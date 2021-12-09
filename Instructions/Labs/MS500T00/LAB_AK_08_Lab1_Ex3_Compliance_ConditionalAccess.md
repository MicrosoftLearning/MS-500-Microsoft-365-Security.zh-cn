# 模块 7 - 实验室 1 - 练习 3 - 创建合规性和条件访问策略 

### 应用场景

Datum 希望确保已注册的 Windows 10 设备符合最低配置规范。  以下条件是必需的：

* 最低 OS 版本：10.0.17763.615
* 需要 Windows Defender 反恶意软件
* iOS 和 MacOS 平台已被阻止

如果设备不符合这些要求，则应将该设备标记为不合规。

#### 任务 1：创建并应用合规性政策和注册限制

1.  以 **ADATUM\Administrator** 身份登录 **LON-CL1**，密码为 `Pa55w.rd`。 

2.  在 Microsoft Edge 浏览器的地址栏中，键入 `https://endpoint.microsoft.com`，然后按 **Enter** 键。以 **admin\@yourtenant.onmicrosoft.com** 身份使用默认租户密码登录。

3.  从导航窗格单击“**设备**”，然后单击“**合规性策略**”。

4.  在 **“合规性策略” | “策略”** 边栏选项卡，在详细信息窗格中，单击“**创建策略**”。

5.  在“**创建策略**”边栏选项卡上，提供以下值，然后单击“**创建**”：

    -  平台：**Windows 10 及更高版本**

6.  在“基本信息”选项卡上，提供以下值并单击“**下一步**”：

    -  名称： `Compliance1`

7.  在“**合规性设置**”选项卡，单击“**设备运行状况**”，然后查看可用的设置。

8.  在“**合规性设置**”选项卡中，展开“**设备属性**”。在“**最低 OS 版本**”字段，键入 `10.0.16299.15`。

9.  在“**合规性设置**”选项卡中，展开“**系统安全**”。向下滚动并将 
    “**Windows Defender 反恶意软件**”设置为“**需要**”。单击“**下一步**”。

10. 在“**非合规性操作**”选项卡中，请注意，“**将设备标记为非合规**”的计划是立即进行的。查看如何配置将设备标记为非合规之后的天数，以及配置其他操作。单击“**下一步**”。 

11. 在“**分配**”选项卡，在“**包含的组**”下面，单击“**+ 添加组**”。单击`Enrolled Devices`，选择“**选择**”，然后单击“**下一步**”。

12. 单击“**创建**”。

13. 从左侧菜单单击“**设备**”，然后单击“**注册设备**”。

14. 在 **“注册设备” | “Windows 注册”** 边栏选项卡上，单击“**注册限制**”。

15. 在详细信息窗格的“**设备类型限制**”部分的“**默认**”行，单击“**全部用户**”。
    
16. 在“**全部用户**”边栏选项卡上，单击“**属性**”。在“**平台设置**”部分，单击“**编辑**”。

17. 在“**平台设置**”选项卡的“**平台**”列中，在包含“**iOS/iPadOS**”和“**macOS**”的行，单击“**阻止**”。单击“**查看 + 保存**”，然后单击“**保存**”。

18. 向左滚动到“**注册设备” | “注册限制**”边栏选项卡。在“**设备限制**”部分，单击“**全部用户**”，然后单击“**属性**”。

19. 在“**设备限制**”部分，单击“**编辑**”，然后将值改为“**3**”。  

20. 单击“**查看 + 保存**”，然后单击“**保存**”。


## 任务 2：创建条件访问策略

### 应用场景 

当设备不合规时，它们应无法访问其电子邮件。你需要配置一个执行此规则的条件访问策略，并验证其是否按预期运行。


1.  在 **LON-CL1** 的 **Microsoft Endpoint Manager 管理中心**，单击“**设备**”然后单击“**条件访问**”。

2.  在 **“条件访问” | “策略”** 窗格中，单击“**+ 新建策略**”。

3.  在“**新建**”边栏选项卡的“**名称**”文本框中，键入 `Conditional1`，然后单击“**用户和组**”。

4.  在“**用户和组**”边栏选项卡，单击“**全部用户**”单选按钮。

5.  在“**新建**”边栏选项卡上，单击“**云应用或操作**”，单击“**选择应用**”单选按钮，单击“**选择**”，单击“**Office 365 Exchange Online**”，然后单击“**选择**”。

6.  在“**新建**”边栏选项卡，单击“**条件**” > “**选择了 0 个条件**”。在“**设备平台**”标签下，单击“**未配置**”。在“**设备平台**”弹出窗口下，在“**配置**”下方单击“**是**”，单击“**选择设备平台**”单选按钮，单击“**Windows**”复选框，然后单击“**完成**”。

7.  在“**新建**”边栏选项的“**访问控制**”下，单击“**授权**”，单击“**要求设备标记为合规**”复选框，然后单击“**选择**”。

8.  在“**新建**”边栏选项卡上，对“**启用策略**”选项单击“**开启**”，然后单击“**创建**”。

#### 任务 3：确认条件访问策略生效

1.  在 **LON-CL2** 上，打开一个新的 Microsoft Edge 选项卡，然后打开 `https://portal.office.com`。

2.  单击“**Outlook**”图标。 

3.  确认收到“**无法从此处访问**”消息或相似警告信息。

4.  单击“**更多详细信息**”。应该可以看到更多有关被阻止原因的详细信息。**备注：** 这是因为 LON-CL1 没有加入 Azure AD，并且没有由 Intune 管理，所以标记为合规。

5.  **关闭**浏览器窗口。

6.  返回到 **LON-CL1**，然后打开 EndPoint Manager。在 Microsoft Edge 浏览器的地址栏中，键入 `https://endpoint.microsoft.com`，然后按 **Enter** 键。以 **admin\@yourtenant.onmicrosoft.com** 身份使用默认租户密码登录。

7.  单击“**设备**”然后单击“**条件访问**”。单击“Conditional1”策略旁的省略号，然后单击“**删除**”。选择“**是**”以确认删除。备注：如果没有删除此策略，它将干扰后面的实验室。



**实验室结束**