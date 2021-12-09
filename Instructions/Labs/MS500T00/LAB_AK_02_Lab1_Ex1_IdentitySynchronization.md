# 模块 2 - 实验室 1 - 练习 1 - 为组织设置标识同步 

你是 Adatum Corporation 的安全管理员 Holly Dickson，并在虚拟实验室环境中部署了 Microsoft 365。在本实验室中，你将在 Microsoft 365 租户帐户和本地 Active Directory 帐户之间实现标识同步。

### 任务 1 - 配置 UPN 后缀

1.	在 LON-DC1 上，使用实验室托管服务提供商分配的密码以 **Adatum\Administrator** 的身份进行登录。
2.	以管理员身份使用 Windows PowerShell，使用“@zzzzzzz.onmicrosoft.com”（其中 zzzzzzz 是唯一 UPN 名称）作为域名更新域的 UPN 后缀和 AD DS 中每个用户的 UPN。为此，请运行以下命令（请记住将 zzzzzzz 更改为唯一的 UPN 名称）：

    	Set-ADForest -identity "adatum.com" -UPNSuffixes @{replace="zzzzzzz.onmicrosoft.com"}  
3.	接下来键入以下命令（请记住将 zzzzzzz 更改为唯一的 UPN 名称）： 

		Get-ADUser –Filter * -Properties SamAccountName | ForEach-Object { Set-ADUser $_ -UserPrincipalName ($_.SamAccountName + "@zzzzzzz.onmicrosoft.com" )}
4.	在 Windows PowerShell 提示符处，键入以下命令并按 Enter：

		Set-ExecutionPolicy Unrestricted  
5.	要确认执行策略更改，请输入表示“是”的 **A**，然后按 Enter。
 
### 任务 2 - 启用目录同步

1.	打开浏览器，并转到 `https://portal.office.com/`   
2.	以 **holly@M365xZZZZZZ.onmicrosoft.com** 的身份和密码 `Pa55w.rd` 登录。    
3.	单击“**管理员**”，转到 Microsoft 365 管理中心。
4.	若系统要求“**更新管理员联系人信息**”，单击“取消”按钮跳过此请求。  
	**备注：** 若看到正在激活 Active Directory 同步的警告，现在可忽略它，但这样就无法在本练习的后面部分中运行目录同步。必须等到目录同步激活。但是，即便确实看到警告消息仍可以完成以下步骤。  
5.	在左侧导航中，选择“**用户**”图标然后选择“**活跃用户**”，单击顶部菜单中的省略号然后选择“**目录同步**”。   
6.	单击“**转到下载中心获取 Azure AD Connect 工具**”。下载并在出现提示后运行下载项。
    
### 任务 3 - 运行 Azure AD Connect

1.	在 Microsoft Azure Active Directory Connect 设置向导上，继续完成向导。 
2.	同意许可条款和隐私声明。
3.	单击“**使用快速设置**”。   
4.	在“**连接到 Azure AD**”屏幕上，输入 Office 365 管理员用户名 
**holly@M365xZZZZZZ.onmicrosoft.com** 和密码 `Pa55w.rd`，然后单击“下一步”。   
5.	如果有弹出登录窗口“**连接到 AD DS**”屏幕，请输入域管理员 **Admin@M365xZZZZZZ.onmicrosoft.com** 和密码“**ycYoe&L20a%%**”，然后选择“**下一步**”。   
6.	在“**连接到 AD DS**”屏幕上，输入域管理员用户名 **ADATUM\Administrator** 和密码 `Pa55w.rd`，然后选择“**下一步**”。   
7.	选中“**继续执行，无需将所有 UPN 后缀与已验证的域匹配**”复选框。在 Azure AD 登录配置屏幕上选择“**下一步**”。   
8.	在“**准备配置**”屏幕中，确保选中“**配置完成后启动同步过程**”复选框，然后选择“**安装**”。   
9.	等待安装完成（这可能需要几分钟）。   
10.	选择“**退出**”。   

### 任务 4 - 验证目录同步结果并授予用户许可。 

1.	要验证创建的新用户，请通过在地址栏中键入 `https://portal.office.com` 在浏览器中打开 Office 365 管理中心。  
2.	使用以下凭据以 Holly Dickson 的身份登录：  用户名：**holly@M365xZZZZZZ.onmicrosoft.com**，密码： `Pa55w.rd`  
3.	导航到“**活跃用户**”。  
4.	现在，应该可以看到许多用户已从本地 Active Directory 同步。可能需要单击刷新按钮来更新页面中的数据。  选择“Abbie Parsons”。  Abbie 是同步之前仅位于 AD DS 域中的用户。 
5.	按如下所示编辑 Abbie Parsons 产品许可证： 
	- 位置 = 英国
	- 产品许可证 = 企业移动性 + 安全性 E5
6.	单击“**保存更改**”以进行更改。关闭窗口。

你已成功将本地 ADATUM 用户同步到 Office 365，并授予同步用户 Abbie Parsons 许可。

# 实验室结束  

 
