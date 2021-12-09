# 模块 1 - 实验室 1 - 练习 1 - 设置 Microsoft 365 租户 

在以下实验室练习中，你将扮演 Adatum Corporation 安全管理员 Holly Dickson 这一角色。Adatum 在本地部署中运行旧版应用程序（例如 Microsoft Exchange）。不过，他们最近订阅了 Microsoft 365，进而创建了混合部署，其中他们必须同步其本地部署和云部署。 

你的任务是使用虚拟化实验室环境在 Adatum 的混合部署中部署 Microsoft 365。在本实验室中，你将设置一个 Microsoft 365 试用租户、添加自定义本地接受的域、安装 Azure Active Directory，并添加多个将在本课程中实验室的其余部分使用的用户和组。 

在本实验室中，已选择试用租户，并已创建一个默认租户管理员帐户。你扮演 Adatum 安全管理员 Holly Dickson 的角色，负责初始安装的剩余操作。你将使用 ADATUM\Administrator 帐户登录到域控制器 VM。在首次访问 Microsoft 365 时，你将先使用分配给 Microsoft 365 租户的租户电子邮件帐户进行登录。为 Holly 创建 Microsoft 365 帐户后，你将以 Holly 的身份登录到 Microsoft 365。


### 任务 1 - 获取 Office 365 凭据

启动实验室后，Microsoft 虚拟实验室环境中将提供一个免费试用租户供你访问 Azure。系统会自动向该租户分配一个唯一用户名和密码。你必须检索此用户名和密码，以便在 Microsoft 虚拟实验室环境中登录 Azure 和 Microsoft 365。系统还将向你的 O365 Blob 分配一个唯一的网络 IP 地址和 UPN 名称。你还将在本课程的所有实验室的各项任务中使用此 UPN 名称。

1. 由于此课程可由学习合作伙伴使用几个授权实验室托管提供者中的任何一个提供，因此检索与租户关联的 UPN 名称、网络 IP 地址和租户 ID 所涉及到的实际步骤可能会因实验室托管提供者而有所不同。因此，讲师将在课程中为你提供有关如何检索此信息的必要说明。你应该记录以供稍后使用的信息包括：

	- **租户后缀 ID。** 此 ID 适用于将在所有实验室中用来登录 Microsoft 365 的 onmicrosoft.com 帐户。其格式为 **{username}@M365xZZZZZZ.onmicrosoft.com**，其中 ZZZZZZ 是实验室托管提供者提供的唯一租户后缀 ID。记录此 ZZZZZZ 值以供稍后使用。当有任何实验室步骤指示你登录 Office 365 或 Microsoft 365 门户时，都必须输入在此处获取的 ZZZZZZ 值。
	- **租户密码。** 这是由实验室托管提供者提供的管理员帐户的密码。
	- **UPN 名称（格式为 XXYYZZa）和网络 IP 地址。** 记下 **IP 地址** 值（这是父域的 IP 地址，例如 64.64.206.13）和 **UPN 名称** （例如 AVEAH2a）。

### 任务 2 - 设置组织资料

你扮演 Adatum 安全管理员 Holly Dickson 的角色，任务是为其 Microsoft 365 试用租户设置公司资料。在此任务中，你将为 Adatum 的租户配置所需的选项。由于 Holly 尚未创建 Microsoft 365 个人用户帐户（你将在任务 3 中执行此操作），Holly 最初将使用实验室托管提供者分配的租户电子邮件地址和密码作为默认 Microsoft 365 MOD 管理员帐户登录 Microsoft 365。

1. 当虚拟机打开时，它会打开客户端电脑 VM (**LON-CL1**)。你需要切换到域控制器 VM (**LON-DC1**)。

2. 以 **ADATUM\Administrator** 身份登录，密码为 `Pa55w.rd`。 

3. 如果收到“**网络**”警告消息，询问你是否希望此电脑可供此网络上的其他电脑和设备发现，请选择“**否**”。

4. 这会自动启动**服务器管理器**。让它保持打开状态（将在下一个任务中用到），但暂时将窗口最小化。

5. 在页面底部的任务栏上，选择“**Internet Explorer**”图标。在浏览器窗口打开时将其最大化。

6. 在浏览器中，在地址栏中输入以下 URL 转到 **Microsoft Office 主页**： `https://portal.office.com/` 

7. 在“**登录**”对话框中，复制粘贴实验室托管提供者提供的**租户电子邮件**帐户，然后选择“**下一步**”。

8. 在“**输入密码**”对话框中，复制粘贴实验室托管提供者提供的**租户密码**，然后选择“**登录**”。

9. 在“**保持登录?**”对话框上，选中“**不再显示此内容**”复选框，然后选择“**是**”。

10. 如果出现“**使用 Office 365 完成工作**”类型窗口，现在请关闭它。 

11. 如果出现“**设置时区**”窗口，请选择“**为日历设置时区**”。在打开的 **Outlook** 窗口中，在“**时区**”下选择你所在时区并选择“**保存**”，然后关闭浏览器窗口，再通过在地址栏输入以下 URL 重新打开 **Microsoft Office 主页**： `https://portal.office.com/`.

16. 如果出现“**早上好/下午好/晚上好 MOD 管理员**”窗口，请选择“**开始使用**”。

17. 在 **Microsoft Office 主页**中，选择“**管理员**”应用。这会打开 **Microsoft 365 管理中心**。

18. 在左侧导航窗格中，选择“**全部显示**”省略号 (...) 图标，显示所有导航菜单选项。

19. 在左侧导航窗格中，选择“**设置**”，选择“**组织设置**”，然后选择“**组织资料**”选项卡。

20. 在“**组织资料**”选项卡中选择“**组织信息**”，它会显示 Contoso 作为组织名称，请更改此信息。

    **备注：** 如需了解 Contoso 组织名称，可查看本实验室开头的“简介”部分。在以下步骤中，将其更改为 Adatum Corporation。 

21. 在“**组织信息**”窗口中输入以下信息：

	- 名称： `Adatum Corporation`

	- 地址： `555 Main Street`

	- 城市： `Redmond`

	- 州：**华盛顿州**

	- 邮政编码： `98052`

	- 电话： `425-555-1234`

	- 技术联系人：“**admin@M365xZZZZZZ.onmicrosoft.com**”（其中 ZZZZZZ 是实验室托管提供者提供的唯一租户 ID）

	- 首选语言：**选择你的首选语言**

22. 选择“**保存**”。

23. 关闭“**组织信息**”窗口。

24. 在“设置”窗口中，选择“**版本首选项**”。如果默认设置下未显示“**版本首选项**”，请使用右上角的“搜索所有设置”搜索“版本首选项”

25. 在“**版本首选项**”窗口中，选择“**面向所选用户的目标版本**”，然后选择“**保存**”。

    **备注：** Office 365 的优势之一是能够将最新的功能和更新自动应用于你的环境，这可降低组织的维护成本和开销。通过设置版本首选项，你可以控制 Office 365 租户接收这些更新的方式和时间。

26. 如果出现“**是否确定要更改为面向所选用户的目标版本**”窗口，请选择“**是**”。  <br/>

    **备注：** 通过此选项，你可创建一个将预览更新的用户对照组，以便可为整个组织准备更新。在开发环境中，更常用的是“**面向所有人的目标版本**”选项；在这里，你可为整个组织及早获取更新。在 Adatum 等非开发环境中，更典型的首选项是“面向所选用户的目标版本”，因为它使组织能够控制当对照组审查更新后何时向所有人提供这些更新。

27. 在“**版本首选项**”窗口中，选中“**选择用户**”。

28. 在“**选择目标版本的用户**”窗口中，在用户列表中选择“**MOD 管理员**”，然后选择“**保存**”。

29. 关闭“**版本首选项**”窗口，这将返回到“**设置**”窗口。

30. 选择“**自定义主题**”。

31. 在“**自定义主题**”窗口中，可添加公司的徽标，并将背景图像设置为所有用户的默认图像。除了这些选项，你还可更改导航窗格的颜色、文本颜色、图标颜色和主题色。请继续查看，探索其他一些适合你的租户的选项。执行你希望的任何更改。<br/>

    **备注：** 一些颜色模式会在美学上分散用户的注意力。请不要同时使用几种高对比色，例如将霓虹色和高分辨率颜色（如白色和亮粉色）联用。

32. 完成探索并进行任何进一步更改后，选择“**保存**”，然后选择“**关闭**”。

33. 继续登录到域控制器 VM 并在 Internet Explorer 中，将 Microsoft 365 管理中心选项卡和所有选项卡保持在打开状态来执行其余任务。 
 



### 任务 3 - 创建 Microsoft 365 用户帐户 

Holly Dickson 是 Adatum 的安全管理员。Holly 没有为自己设置 Microsoft 365 个人用户帐户，因此她最初以默认的 Microsoft 365 MOD 管理员帐户身份登录到 Microsoft 365。在此任务中，她将为自己创建一个 Microsoft 365 用户帐户，并将为其用户帐户分配 Microsoft 365 全局管理员角色，这使她能够在 Microsoft 365 中执行所有管理功能。

‎之后，你将在 Microsoft 365 管理中心创建其他几个用户帐户，每个帐户稍后将添加到新的安全组中（你还将创建这些安全组）。虽然安全管理员通常不会添加用户帐户，但此任务只执行一次；若要准备 Adatum 的测试环境供本课程中的后续实验室练习使用，则需要执行此任务。

**重要提示：** 在实际部署中，最佳做法是始终记下第一个全局管理员帐户的凭据（在本实验室中为 MOD 管理员），并出于安全原因存储该凭据。此帐户是一个非个性化的标识，它在租户中拥有尽量最高的权限。此帐户**未**激活 MFA（因为它非个性化），并且其密码通常在多名用户之间共享。因此，第一个全局管理员非常容易遭到攻击，建议创建个性化的服务管理员并尽量减少全局管理员的数量。对于你创建的全局管理员，每一个都应映射到单一标识，而且每个都该强制执行 MFA。

1. 在 **LON-DC1** VM 上，**Microsoft 365 管理中心**自上一任务以来应仍然在 Internet Explorer 中保持打开状态。在 **Microsoft 365 管理中心**的左侧导航窗格中，选择“**用户**”，然后选择“**活动用户**”。 

2. 在“**活动用户**”列表中，你将看到默认的 **MOD 管理员**帐户和其他一些用户帐户。由于你在此实验室场景中扮演 Holly Dickson 的角色，因此你将为自己创建一个用户帐户，并为自己分配 Microsoft 365 全局管理员角色。 

3. 在“**活动用户**”窗口中，选择“**添加用户**”。 

4. 在“**设置基本信息**”窗口中，输入以下信息：

	- 名字： `Holly`

	- 姓氏： `Dickson` 

	- 显示名称：点击进入此字段时，将显示“**Holly Dickson**”。

	- 用户名：点击进入此字段时，可能会显示“**Holly**”；如果未显示，则输入它用作用户名
	
		‎**重要提示：** “**用户名**”字段的右侧是域字段。它可能预先填充了自定义的 **XXYYZZa.CustomDomain.us** 本地域；但是，必须选择下拉箭头，改为选择 **M365xZZZZZZ.onmicrosoft.com** 云域（其中 ZZZZZZ 是实验室托管提供者提供的租户 ID）。
	
		配置此字段后，Holly 的用户名应显示为：

		**Holly@M365xZZZZZZ.onmicrosoft.com**  
	
	- 密码设置：取消选中“**自动创建密码**”选项

	- 密码： `Pa55w.rd`

	- 取消选中“**要求此用户在首次登录时更改其密码**”复选框。 

5. 选择“**下一步**”。

6. 在“**分配产品许可证**”窗口中，输入以下信息：

	- 选择位置：**美国**

	- 许可证：在“**向用户分配产品许可证**”下，选择“**Microsoft 365 E5**”和“**企业移动性 + 安全性 E5**”。 

7. 选择“**下一步**”。

8. 在“**可选设置**”窗口的“角色”部分，选择“**管理中心访问权限**”。这样，所有 Microsoft 365 管理员角色现在都已启用并可分配。

10. 选择“**全局管理员**”，然后选择“**下一步**”。

11. 在“**查看并完成**”窗口中，查看所选内容。如需更改任何内容，请选择相应的“**编辑**”链接并进行必要的更改。如果一切正确，请选择“**完成添加**”。 

12. 在“**Holly Dickson 已添加到活动用户**”页面上，选择“**关闭**”。 
‎
14. 保持登录到域控制器 VM，同时将浏览器中的 Microsoft 365 管理中心保持在打开状态来执行下一个任务。





### 任务 4 - 准备 Microsoft Azure Active Directory 

安装 Microsoft 365 时，需要 Azure Active Directory 来执行多个配置步骤。这些步骤是使用 Windows PowerShell 执行的。但是，在可以使用 PowerShell 访问 Azure AD 之前，必须先安装 Windows PowerShell 模块，这让你能够通过 PowerShell 访问 Azure AD。在此任务中，你将通过安装这些 PowerShell 模块来准备好使用 Azure AD。

1. 通过执行以下步骤打开 **Windows PowerShell**：

	- 选择屏幕底部任务栏上的放大镜（搜索窗口）图标，然后在出现的搜索框中键入“**powershell**”。 

	- 在显示的菜单中，右键单击“**Windows PowerShell**”，然后在下拉菜单中选择“**以管理员身份运行**”。 

1. 在“**Windows PowerShell**”中，键入以下命令，然后按 Enter：

	‎`Install-Module MSOnline` 
	
1. 如果系统提示安装 **NuGet 提供程序**，请输入“**Y**”来选择“**[Y] 是**”。按 Enter 键。 

1. 如果系统提示从 **PSGallery** 安装模块，请输入“**A**”来选择“**[A] 全是**”。按 Enter 键。

1. 安装完成后，屏幕将返回到 Windows PowerShell 命令提示符。

1. 然后，必须运行以下命令，安装刚才在上一步骤中检索到的 Azure AD PowerShell 模块：

	`Install-Module AzureADPreview`   
	
1. 如果系统提示确认是否要执行此命令，请输入“**A**”来选择“**[A] 全是**”。

1. 现在，你已安装了访问 Azure AD 所需的 Windows PowerShell 模块。

1. 继续登录到域控制器 VM，并将 Windows PowerShell 窗口保持在打开状态。


### 任务 5 - 为 SharePoint Online 启用 IRM 

在此任务中，你将为 SharePoint Online 启用信息权限管理 (IRM)。 

**备注：** 虽然你将在稍后的实验室中验证 Exchange 和 SharePoint 中的 IRM，但现在必须为 SharePoint Online 启用 IRM，因为 IRM 可能需要 60 分钟或更长时间才能显示在 SharePoint Online 中。等到你在稍后的实验室中进行验证练习时，IRM 应该已完成其内部配置，因此你不必等待它出现在 SharePoint Online 中。

1. 你仍应使用 **LON-DC1\Admin** 帐户和密码 **Pa55w.rd** 登录到域控制器 VM，而且你仍应以 **MOD 管理员**身份登录到 Microsoft 365 (portal.office.com)。 

2. 在 **Microsoft 365 管理中心**，向下滚动浏览左侧导航窗格，然后在“**管理中心**”下选择“**SharePoint**”。这将打开 SharePoint 管理中心。

3. 如果出现“**SharePoint 管理位置**”弹出窗口，请选择“**明白了**”以关闭窗口。

4. 在 **SharePoint 管理中心**的左侧导航窗格中，选择“**设置**”。 

5. 页面底部显示“找不到所需的设置? **请转到经典设置页面。”** 在此消息中，选择超链接文本：“**经典设置页面**”。

6. 在“**设置**”页面上，向下滚动到“**信息权限管理(IRM)**”部分，选择“**使用配置中指定的 IRM 服务**”，选择“**刷新 IRM 设置**”按钮，然后向下滚动到页面底部并选择“**确定**”。 

7. 请勿关闭 Microsoft Edge 浏览器中的 SharePoint 管理中心选项卡。将浏览器保持在打开状态来执行下一个任务。

### 任务 6 - 打开审核日志以启用警报策略

在稍后的实验室中，你将使用安全与合规中心创建警报策略。但是，管理员必须先为组织打开审核日志，然后你才能实现警报。在安全与合规中心打开审核日志后可能需要几个小时才能完全启用它，因此你将在本实验室中将其打开，以便等到你执行稍后的实验室时，它已完全启用。

1. 你仍应使用 **LON-DC1\Admin** 帐户登录域控制器 1 VM，而且应以 **MOD 管理员**身份登录到 Microsoft 365。

2. 在浏览器的地址栏中，输入以下 URL： `https://protection.office.com`。

3. 在 **Office 365 安全与合规中心**的左侧导航窗格中，选择“**搜索**”，然后在其下方选择“**审核日志搜索**”。

4. 在“**审核日志搜索**”窗口的页面右上角，选择“**启用审核**”，然后选择“**是**”来确认“**你的组织设置需要进行更新，是否继续?**”。备注：对于 MS 365 和 Office 365 企业版组织，默认开启“审核日志”。如果该页面没有提示“开启”审核日志，则表示“审核日志”已默认开启。

5. 使客户端 1 VM 和安全与合规中心保持在打开状态。




# 实验室结束 