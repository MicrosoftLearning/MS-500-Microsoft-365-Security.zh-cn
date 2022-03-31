---
ms.openlocfilehash: f47aa7a96acf20bb7b610018a31215cc95be604f
ms.sourcegitcommit: 25b9793190d40e69ed31815267fb6754397768bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "137943294"
---
# <a name="module-1---lab-2---exercise-1---configure-self-service-password-reset-sspr-for-user-accounts-in-azure-ad"></a>模块 1 - 实验室 2 - 练习 1 - 在 Azure AD 中为用户帐户配置自助式密码重置 (SSPR)


### <a name="scenario"></a>方案

支持人员指出大量支持票证与密码重置有关。 你需要设置一种方法供用户自行重置其密码。 



#### <a name="task-1-enable-self-service-password-reset"></a>任务 1：启用自助式密码重置

1.  切换到 LON-CL1，然后以 Adatum\\Administrator 的身份和密码 Pa55w.rd 进行登录。  

2.  在任务栏上选择“Microsoft Edge”，转到 `https:/portal.azure.com/` 打开 Azure。  使用上一实验室中的 Holly Dickson 身份进行登录。 导航到 Azure Active Directory
    

3.  在导航窗格中，选择“用户”，然后选择“密码重置”。 

4.  在“密码重置 | 属性”窗口中选择“全部”，为所有用户启用自助式密码重置。  选择“保存”  。

5.  在“密码重置 | 管理”边栏选项卡上，选择“身份验证方法”。 

6.  对于用户可用的方法，请确保选择了“移动电话(仅发送短信)”和“电子邮件”，然后选择“安全性问题”。  

7.  在“注册所需的问题数”中选择“3” 。

8.  在“重置所需的问题数”中选择“3” 。

9.  在“选择安全问题”部分，选择“未配置安全问题”，然后选择“预定义”  。 选择三个问题，然后选择两次“确定”。

10. 选择“保存”  。

11. 仍在“密码重置 | 管理”边栏选项卡上，选择“注册”，为“要求用户登录时注册”选择“否”，然后选择“保存”。    

#### <a name="task-2-register-user-for-self-service-password-reset"></a>任务 2：为用户注册自助式密码重置

启用并配置 SSPR 后，使用在上一部分选择的组（例如 Test-SSPR-Group）中的用户测试 SSPR 过程。 以下示例使用了 testuser 帐户。 提供你自己的用户帐户，该帐户属于你在此迷你实验室的第一部分为 SSPR 启用的组。

>注意：在测试自助式密码重置时，请使用非管理员帐户。 始终为管理员启用自助式密码重置，且管理员需要使用两种身份验证方法来重置其密码。

1.   在 Web 浏览器的页面右上角，选择你的帐户名称，然后选择“注销”。 

2.  使用实验室托管服务分配的密码以 AllanD@yourtenant.onmicrosoft.com 身份登录。   

1. 浏览至自助式密码注册页面 [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup)。

1. 在“安全信息”页面上，单击“添加方法” 。 选择所需的身份验证方法（例如电话），然后继续执行设置步骤。

>注意：如果系统提示使用电子邮件，则需要使用电子邮件地址，而非为本实验室提供的租户域名。 若没有可用电子邮件地址，可以跳过电子邮件验证，然后继续下一步。 登录电子邮件帐户，阅读代码，将其键入验证字段，然后选择“验证”。 
    
>注意：若未在收件箱中找到含有代码的邮件，请检查垃圾邮件文件夹。

#### <a name="task-3-test-self-service-password-reset"></a>任务 3：测试自助式密码重置

1. 转到 `https://aka.ms/sspr` 并输入 Alan 的用户名 (AllanD@yourtenant.onmicrosoft.com)。 在下面填写 Captcha，然后单击“下一步”。

1. 使用上一任务中配置的方法请求验证。

11. 输入收到的验证码，然后单击“下一步”。

12. 输入新密码，然后单击“完成” 。

# <a name="continue-to-lab-2---exercise-2"></a>继续进行实验室 2 - 练习 2
