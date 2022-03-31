---
ms.openlocfilehash: 5a2da44f089e10048a0d928df82ef6dd66840a87
ms.sourcegitcommit: 25b9793190d40e69ed31815267fb6754397768bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "137943308"
---
# <a name="module-5---lab-1---exercise-1---implement-atp-policies"></a>模块 5 - 实验室 1 - 练习 1 - 实现 ATP 策略  

你为 Holly Dickson 设置了全局管理员帐户，并且以 Holly 的身份登录了 Microsoft 365。 在 Adatum 试点项目的此阶段，你希望编辑现有的 ATP 安全链接策略，然后创建安全附件策略，并为 SharePoint、OneDrive 和 Microsoft Teams 启用高级威胁防护。 你还将验证这两个策略以确保它们正常工作。

### <a name="task-1--create-a-safe-links-policy"></a>任务 1 - 创建安全链接策略

在此任务中，你将向公司范围的阻止 URL 列表中添加 URL http://tailspintoys.com ，并且将创建适用于租户中所有用户的 ATP 安全链接收件人策略。

1. 你仍应使用 LON-CL1\Admin 帐户登录到客户端 1 VM (LON-CL1)，并且仍应以 Holly Dickson 的身份登录到 Microsoft 365。  

2. 你仍应位于 Microsoft 365 安全与合规中心。 如果没有，请在浏览器中输入 `https://protection.office.com`

3. 在“安全与合规中心”的左侧导航窗格中，选择“威胁管理”，然后选择“策略”。  

4. 在“策略和规则”窗口中，选择“安全链接”。 

5. 在“安全链接”窗口中，单击“全局设置”。 

6. 在“活动安全链接策略中包含的用户的全局设置”窗口的“阻止以下 URL”部分下，可以输入要阻止的任何 URL 。 对于此测试实验室，在“输入有效 URL”字段中，输入 `http://tailspintoys.com` 以将其添加到策略中。

7. 选择“保存”  。

8. 选择“+ 创建”以添加新的收件人策略。

9. 在“命名策略”窗格上，在“名称”字段中为实验室会话 `Unique Name` 输入唯一名称。  单击“下一步”。

10. 在“用户和域”窗格中，在“组”字段中输入 `All Company`，从列表中选择它。  单击“下一步”。

11. 在“保护设置”窗格上，选择以下选项，然后单击“下一步” ：

    - 在“选择针对邮件中未知潜在恶意 URL 的操作”下：选择“开 - 当用户单击链接时，将重写 URL 并根据已知恶意链接列表进行检查”。

    - 对于 Microsoft Teams 中的未知或潜在恶意 URL，也请选择“开”。

    - 选中“对可疑链接和指向文件的链接应用实时 URL 扫描”旁边的复选框。

    - 选中“将安全链接应用于组织内发送的电子邮件”旁边的复选框。

12. 在“通知”窗格中，保留选中的默认通知文本。 单击“下一步”。

13. 在“查看”窗格中，选择“提交”以创建策略 。

14. 将“Office 365 安全与合规”选项卡保持打开状态，以便在稍后的任务中使用。

### <a name="task-2--validate-the-safe-links-policy"></a>任务 2 - 验证安全链接策略

在此任务中，你将测试刚刚创建的安全链接策略，该策略会阻止指向 `http://tailspintoys.com` URL 的链接。

1. 你仍应使用 LON-CL1\Admin 帐户登录到客户端 1 VM (LON-CL1)，并且应该以 Holly Dickson 的身份登录到 Microsoft 365。  

2. 在 Microsoft Edge 浏览器中，选择“Microsoft Office 主页”（或转到 `https://office.com`）选项卡，然后选择 Outlook。  

3. 如果你收到“我们已更新 Outlook”消息，请选择“以后再说”，或者如果你看到“欢迎”消息，请将其关闭  。

4. 在 Outlook 网页版中，在屏幕的左上方选择“新建邮件” 。

5. 在右侧窗格中，输入以下电子邮件信息：

    - 更改为：你将向 MOD 管理员发送电子邮件，因此在“收件人”字段中输入 mod，然后从下拉列表中选择“MOD 管理员”电子邮件地址  。

    - 添加主题：`Free stuff from Microsoft`

    - 添加消息：`Please click on me for free toys from Microsoft`

6. 选择你在邮件正文中添加的文本。

7. 在详细信息窗格底部，邮件正文的下方是任务栏。 在任务栏上，选择“插入超链接”图标以显示“插入链接”窗口。

8. 在“插入链接”窗口中，你在邮件正文中突出显示的文本应显示在“显示为”字段中 。 在“Web 地址(URL)”字段中，输入以下 URL：`http://tailspintoys.com/aboutus/freetoys`。

9. 选择“确定”。

10. 在电子邮件正文中，该消息仍应处于选中状态。 单击邮件正文中的任意位置以删除突出显示。 文本的颜色现在应该是蓝色，并且应该带有下划线，表明此消息是指向 URL 的超链接。

11. 在消息上方显示的菜单栏中选择“发送”（或选择页面底部的“发送”按钮） 。

12. 现在，你想要在 Outlook 中打开 MOD 管理员的收件箱，并验证你在之前的任务中创建的 ATP 策略是否适用于你刚刚从 Holly 发送的电子邮件。 为此，必须切换客户端 2 VM (LON-CL2)。

13. 如有必要，通过在“密码”字段中输入 Ps55w.rd 以管理员帐户登录 VM  。

14. 选择任务栏中的 Microsoft Edge 图标，最大化窗口，然后在地址栏中输入以下 URL：`https://outlook.office365.com`

15. 由于你希望以 MOD 管理员的身份登录，因此请在“登录”窗口中输入 admin@M365xZZZZZZ.onmicrosoft.com（其中 ZZZZZZ 是实验室托管提供程序提供的租户 ID），然后选择“下一步”。  

16. 在“输入密码”窗口中，输入实验室托管提供程序提供的密码，然后选择“登录”。   如果要求你提供自助式密码信息，请单击“取消”。

17. 选择“从不”关闭“让 Microsoft Edge 保存此站点的密码并在下一次时填写?”横幅 。

18. 在“保持登录?”对话框上，选中“不再显示此内容”复选框，然后选择“是”  。

19. 关闭显示的“欢迎”窗口。

20. 在 MOD 管理员的收件箱中，打开 Holly 发送的电子邮件。

21. 当你将鼠标悬停在电子邮件正文中显示的蓝色链接上时，可以在浏览器窗口底部看到一个长 URL；此 URL 以 `https://nam03.safelinks.protection.outlook.com` 开头。

    当你选择该超链接将其打开时，Edge 中会打开一个新选项卡，显示以下警告消息：打开此网站可能不安全。 此消息表示你的 ATP 安全链接策略运行正常，并且 ATP 安全链接阻止了对此 URL 的访问。

22. 将客户端 2 VM 保持打开状态，并在 Outlook 中保持打开 MOD 管理员的收件箱，以便稍后使用。

### <a name="task-3--create-a-safe-attachment-policy-and-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>任务 3 – 为 SharePoint、OneDrive 和 Microsoft Teams 创建安全附件策略并启用 ATP

在此任务中，你将创建一个 ATP 安全附件策略，该策略将测试发送给 M365xZZZZZZ.on microsoft.com 域内的收件人的电子邮件附件是否包含恶意软件。 你将配置该策略，以便在附件被阻止时从发送给收件人的电子邮件中删除该附件，并将该电子邮件的副本重定向到 Joni Sherman 以供进一步审查。

1. 切换回客户端 1 VM (LON-CL1)。 你仍应使用 LON-CL1\Admin 帐户登录到客户端 1 VM，并且应该以 Holly Dickson 的身份登录到 Microsoft 365 。

2. 在 Edge 浏览器中，选择“Office 365 安全与合规”选项卡。 

3. 在“Office 365 安全与合规中心”的左侧导航窗格中，在“威胁管理”下选择“策略”。  

4. 在“策略和规则”窗口中，选择“安全附件”。 

5. 在“安全附件”窗口中，在“保护 SharePoint、OneDrive 和 Microsoft Teams 中的文件”部分的“全局设置”下的页面顶部，选择“启用适用于 SharePoint、OneDrive 和 Microsoft Teams 的 Defender for Office 365”开关   。 选择“保存”  。

6. 选择菜单栏上的“+ 创建”以添加新的安全附件策略。

7. 在新的安全附件策略窗口中，在“名称”字段中输入 `AttachmentPolicy1`，然后选择“下一步”。 

8. 在“用户和域”中，在“用户”字段中输入 `All Company`，然后选择“下一步”。  

9. 在“安全附件未知恶意软件响应”部分下，选择“动态传递”（此选项仍将发送电子邮件，但将保留附件，直到附件经过扫描并标记为可接受） 。

10. 在“重定向具有检测到的附件的邮件”部分下，选择“启用重定向” 。

11. 在“向指定电子邮件地址发送包含被阻止、受监视或被替换的附件的邮件”字段中，输入 JoniS@M365xZZZZZZ.onmicrosoft.com（其中 ZZZZZZ 是实验室托管提供程序提供的唯一租户 ID），选择“下一步”  

1. 在“查看”窗口中，请注意显示的关于已选择的“安全附件检测响应:”和“重定向附件:”选项的两条消息。   选择“提交”。

12. 更新组织设置可能需要一分钟左右的时间。 在“更新完成”窗口中，选择“确定” 。

**注意：** 遗憾的是，我们无法创建可用于在其中验证刚刚创建的 ATP 安全附件策略的训练实验室。 为此，你必须发送一封包含恶意附件的电子邮件。 可使用一些常见的测试病毒，例如 EICAR 测试病毒；但是，附加已知测试病毒（如 EICAR）的邮件在 Office 365 ATP 对其进行处理之前就会被隔离。 由于 ATP 安全附件功能旨在防范未知和零日病毒及恶意软件，因此创建此类附件非常困难，也不推荐这样做。

也就是说，在实际环境中定义 ATP 安全附件策略后，查看服务工作情况的一种方法是查看高级威胁防护报告。 有关使用 ATP 报告验证安全链接和安全附件策略的详细信息，请参阅[查看 Office 365 高级威胁防护报告](https://docs.microsoft.com/en-us/office365/securitycompliance/view-reports-for-atp)。


# <a name="end-of-lab"></a>实验室结束
