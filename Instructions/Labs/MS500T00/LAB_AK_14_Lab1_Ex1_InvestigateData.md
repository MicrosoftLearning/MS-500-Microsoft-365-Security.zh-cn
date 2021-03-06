# 模块 14 - 实验室 1 - 练习 1 - 调查 Microsoft 365 数据


你扮演 Adatum 安全管理员 Holly Dickson 的角色，已将 Microsoft 365 部署到虚拟化实验室环境中。你正在继续 Microsoft 365 试点项目，现在希望就 Adatum 如何调查其 Microsoft 365 数据进行测试。你决定重点对删除的电子邮件进行内容搜索（这是 Adatum 环境中的一个常见请求），然后你想通过创建一个电子数据展示案例来分析电子数据展示功能。你将通过创建一个 GDPR 数据主体请求来总结试点项目的这一部分。

### 任务 1 - 对已删除的电子邮件执行内容搜索

在本练习中，你将添加 Joni Sherman 和 Holly Dickson 作为电子数据展示管理员角色成员，然后你将以 Joni 的身份登录到客户端 VM，并执行内容搜索，以查找包含与社会安全号码相关的关键字的电子邮件。

1. 你仍应使用 **LON-CL1\Admin** 帐户登录到客户端 1 VM (LON-CL1)，并且应该以 **Holly Dickson** 的身份登录到 Microsoft 365。 

2. 在 **Microsoft Edge** 浏览器中，如果你打开了一个“**安全与合规中心**”选项卡，则选择它；否则，打开一个新选项卡，并在地址栏中输入以下 URL：`https://protection.office.com`。

3. 在“**Office 365 安全与合规中心**”的左侧导航窗格中选择“**权限**”。

4. 在 **“主页”>“权限”** 页面，选择“**电子数据展示管理员**”复选框。

5. 在“**电子数据展示管理员**”角色组窗口中，向下滚动到“**电子数据展示管理员**”部分，选择“**编辑**”。

6. “**编辑选择电子数据展示管理员**”向导打开。列表应为空。选择“**选择电子数据展示管理员**”。

7. 在“**选择电子数据展示管理员**”窗口，选择“**(+) 添加**”。

8. 在显示的用户列表中，选择`Joni Sherman`和`Holly Dickson`，然后选择“**添加**”。  

    **备注：** 你要将 Joni 添加到电子数据展示管理员角色组，以便稍后在本练习中使用，并将 Holly 分配到角色组，以在下一个练习中使用。

9. 你应该会看到一个包含“**2 个成员已添加**”消息的横幅。依次选择“完成”、“**保存**”。

10. 切换到客户端 2 VM (**LON-CL2**)。你应仍使用“**LON-CL2\Admin**”帐户登录“**LON-CL2**”，并且应该以“**Joni Sherman**”的身份登录 Microsoft 365。在“**登录**”窗口，输入“**JoniS@M365xZZZZZZ.onmicrosoft.com**”（其中 ZZZZZZ 是实验室主机提供程序提供的唯一租户 ID）。选择“**下一步**”。在“**输入密码**”窗口中，输入 Joni 的密码（提示：它可能与实验室主机托管服务提供商分配的 MOD 密码相同）。

11. 如果你已在 **Microsoft Edge** 浏览器中打开了“**Office 365 安全与合规中心**”的选项卡，则现在选择它。否则，选择新的选项卡，并在地址栏中输入以下 URL：`https://protection.office.com`。

12. 在“**安全与合规中心**”的左侧导航窗格中，选择“**搜索**”，然后在它的下方选择“**内容搜索**”。  

    ‎**备注**：如果没有在导航窗格中看到“**搜索**”，则需要在“**安全和合规中心**”重新加载浏览器选项卡。

13. 在“**内容搜索**”窗口的“**搜索**”选项卡中，选择顶部菜单上的“**(+) 引导式搜索**”。这将启动“**新建搜索**”向导。

14. 在“为搜索命名”页面，在“**名称**”字段中输入`Content Search Test`，然后选择“**下一步**”。

15. 在“位置”页面上，选择“**所有位置**”，然后选择“**下一步**”。

16. 在“**条件卡**”页面上，输入`SSN`，按 Enter，并在“**关键字**”框中输入`social`。  在关键字之间按 Enter 会将字词分隔为列表中的独立术语。添加这两个术语后，选择“**完成**”。

17. 返回“**搜索**”选项卡，搜索查询将运行。屏幕左下角的“状态”字段将指示查询是否完成。运行查询以及在右侧窗格中显示数据可能需要许多分钟。内容搜索完成后，你将看到为自定义 DLP 策略的敏感信息测试创建的所有邮箱项目。  

如果在课程前面的 DLP 实验室期间未发送过电子邮件，则本次搜索中不会出现任何数据。  如果发生这种情况，在搜索运行时，可以切换回“**LON-CL1**”，并向租户中的其他用户发送带有本实验室中提到的关键字术语的电子邮件。  如果进行了该操作，可能需要再次运行此搜索以查看数据。

可以在继续学习本练习的剩下部分时让搜索保持运行。 

18. 保持客户端 2 VM 以及所有浏览器选项卡的打开状态，继续执行下一个任务。

你已经成功地为 Joni 分配了一个电子数据展示角色，并在租户的所有位置执行了针对特定关键字的内容搜索。

 

### 任务 2 - 创建电子数据展示案例

在本任务中，你将创建一个电子数据展示案例，该案例配置了保留和内容搜索，以查找与社会安全号码相关的任何违规行为。你将继续使用 Joni Sherman 的用户账号。Joni 在前面的任务中分配有电子数据展示管理员角色，因此拥有创建电子数据展示案例所需的权限。

1. 你应仍用“**LON-CL2\Admin**”帐户登录客户端 2 VM (**LON-CL2**)，并应以 Joni Sherman 的身份登录 Microsoft 365。但是，如果已经注销 Microsoft 365，则可以在 Microsoft 365 登录页面上，使用实验室主机托管服务提供商分配的密码登录到 Joni 的“**JoniS@M365xZZZZZZ.onmicrosoft.com**”帐户。

2. “**安全与合规中心**”选项卡应仍然在 Microsoft Edge 中保持打开状态。如果是，现在选择该选项卡。如果已关闭，请在地址栏中输入以下 URL：`https://protection.office.com`。 

3. 在“**安全与合规中心**”的左侧导航窗格中选择“**电子数据展示**”，并在它的下方选择“**电子数据展示**”。

4. 在“**电子数据展示**”窗口的顶部菜单中选择“**(+) 创建案例**”。

5. 在“**新建案例**”窗口的“**案例名称**”字段中输入`Social Security Violation`，并选择“**保存**”。

6. 回到“**电子数据展示**”页面，选择出现在“**社会安全违规行为**”案例左侧的“**打开**”。

7. 在“**社会安全违规行为**”窗口的顶部菜单中选择“**保留**”选项卡。

8. 选择“**(+) 创建**”以创建一个新的保留。这将启动“**新建保留**”向导。

9. 在“**为你的保留命名**”页面，在“**名称**”字段中输入`Social Security Violation - Content`，然后选择“**下一步**”。

10. 在“**选择位置**”页面，对于“**Exchange 电子邮件**”位置，选择“**选择用户、组或团队**”字段。

12. 在“**Exchange 电子邮件**”页面上，选择“**选择用户、组或团队**”。

13. 在搜索字段中输入“**Holly**”，选择字段右侧的搜索图标。 

13. 向下滚动页面，在“**用户、组或团队**”下方，从搜索结果中选择“**Holly Dickson**”。

14. 选择“**选择**”，然后选择“**完成**”。

15. 在“**选择位置**”页面，“**Exchange 电子邮件**”右侧显示“**1 个用户、组或团队**”。选择“**下一步**”。

16. 在“**查询条件**”页面，输入`SSN`，按 Enter，然后在“**关键字**”框中输入`social`。它会单独搜索这两个术语。然后选择“**下一步**”。

17. 在“**查看设置**”页面上查看这些值，并在需要修改的值旁边选择“**编辑**”。如果你对设置感到满意，选择“**创建该保留**”，然后选择“**关闭**”。

18. 回到“**电子数据展示案例概述**”，在 **“社会安全违规行为”>“核心 ED”>“保留”** 页面，从顶部菜单中选择“**搜索**”选项卡。

19. 选择“**(+) 新建搜索**”，然后在下拉菜单中选择“**(+) 新建搜索**”。

20. 在“**新建搜索**”窗口的左侧“**搜索查询**”窗格中，输入`SSN`，按 Enter，在“**关键字**”字段中输入`social`，然后在“**位置**”下，选择“**保留位置**”。

21. 选择“**保存并运行**”。

22. 在“**保存搜索**”窗口中的“**名称**”字段中键入`Social Security Violation - Search`，然后选择“**保存**”。

23. 这将启动一个查找关键字“**SSN**”的搜索查询。查询完成后，等待显示预览结果。 

现在你已经创建了一个电子数据展示案例，添加了一个就地保留以保留邮箱内容，并创建了一个搜索以从保留中发现数据。


# 继续进行练习 2
