---
ms.openlocfilehash: 397874515c8917f273934a99ee38bb5211fb6403
ms.sourcegitcommit: 25b9793190d40e69ed31815267fb6754397768bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "137943260"
---
# <a name="module-6---lab-1---exercise-1---conduct-a-spear-phishing-attack"></a>模块 6 - 实验室 1 - 练习 1 - 进行鱼叉式网络钓鱼攻击


Holly Dickson 担心她组织中的一些用户可能需要学习网络钓鱼攻击。  在本实验室中，你将使用 Microsoft 365 攻击模拟器来确定用户对钓鱼攻击的敏感度。


### <a name="task-1-enable-mulit-factor-authentication-for-holly-dickson"></a>任务 1：为 Holly Dickson 启用多重身份验证


1.  在 LON-CL1 中，转到 Office 365 安全与合规中心 `https://protection.office.com`，并以 Holly Dickson 的身份登录。

2.  单击“威胁管理”，然后单击“攻击模拟器” 。

3.  请注意“必须启用多重身份验证(MFA)”警告。  你即将进行模拟攻击，系统想要确认你的凭据。 这是攻击模拟器的一项要求。 我们来为 Holly Dickson 启用 MFA。 转到浏览器选项卡 Microsoft 365 管理中心，或者打开一个新的浏览器选项卡 `https://admin.microsoft.com`。

    **注意：** 如果你在之前的实验室中为 Holly 启用了 MFA 并使用同一租户，则可能不会收到此警告。  如果是这种情况，可以跳到下一个任务。

4.  在左侧，选择“用户”，然后选择“活动用户” 。

5. 在顶部窗格中的“活跃用户”屏幕上，单击“多重身份验证”。

7.  在“多重身份验证”屏幕中，查看“全局管理员”，然后选择“Holly Dickson”并在快速步骤下选择“启用”  。

8.  在“关于启用多重身份验证”屏幕上，选择“启用多重身份验证”按钮。

9.  在“更新成功”屏幕中单击“关闭”。

10.  关闭浏览器会话。  打开新浏览器并打开 Office 365 安全与合规门户，然后以 Holly Dickson 的身份再次登录。  现在，在登录过程中，系统应会要求你提供多重凭据。

    备注：此 MFA 设置可能需要几分钟时间来传播你的租户。  如果攻击模拟器中的“启动攻击”按钮不可用，请等待几分钟，然后以 Holly Dickson 的身份再次登录。 如果你不能使自己的移动设备满足 MFA 要求，将无法完成本实验室。

### <a name="task-2-configure-and-launch-a-spear-phishing-attack"></a>任务 2：配置并启动鱼叉式网络钓鱼攻击

1. 转到 [Microsoft 365 安全中心 - 攻击模拟训练](https://security.microsoft.com/attacksimulator) ，并以 Holly Dickson 的身份登录。

2. 单击“模拟”选项卡。选择“+ 启动模拟”。

3. 在“选择技术”屏幕上。 确保已选中“凭据搜集”。 单击“下一步”。

4. 命名模拟 `Spear Simulation`，然后选择“下一步”。

5. 在“选择有效负载”屏幕上，从提供的有效负载列表中选择所需的有效负载。 单击“下一步”。

6. 在“目标用户”屏幕中执行以下操作：
    1. 确保已选中“仅包括特定用户和组”。 
    1. 单击“添加用户”。  
    1. 在“添加用户”屏幕上，在搜索框中键入 Patti Fernandez，然后按 Enter 。 
    1. 从搜索结果列表中选择该用户。 
    1. 单击底部的“添加 1 个用户”。 
    1. 单击“下一步”。

7. 保留“分配训练”屏幕上的默认设置。 单击“下一步”。

8. 在“登陆页面”屏幕上，单击“下一步”。 

9. 在“选择最终用户通知”屏幕上，选择“Microsoft 默认通知 (建议)”。

10. 选择“交付首选项”，然后选择“在市场活动期间交付”。 单击“下一步”。

11. 在“启动详细信息”页面上，确保已选中“完成后立即启动此模拟” 。 单击“下一步”。

12. 在“查看模拟”屏幕上，单击“提交” 。 单击“完成”

### <a name="task-3-confirm-target-received-phishing-email-attack"></a>任务 3：确认目标收到钓鱼电子邮件攻击

1.  在 InPrivate 或 incognito 模式下打开新的浏览器窗口并浏览到 `https://office.com`。

2.  以用户 **PattiF@M365xZZZZZZ.onmicrosoft.com** 的身份登录，其中 ZZZZZZ 是你的特定 Office 365 租户。 Patti 的密码可能与你的实验室托管提供程序提供的 MOD 管理员密码相同。

3.  单击 Outlook 图标以为 Patti 打开 Microsoft Outlook。 你应该会看到一封鱼叉式网络钓鱼电子邮件，其中包含你刚刚在上一个任务中输入的详细信息。

### <a name="task-4-review-the-results"></a>任务 4：查看结果

1. 在你以 Holly Dickson 的身份登录的浏览器会话中，返回到[攻击模拟训练](https://security.microsoft.com/attacksimulator)。 单击“模拟”选项卡。

2. 在“模拟详细信息”区域中，注意实际和预测的入侵几率。

3. 单击“鱼叉式网络钓鱼”模拟，然后在“模拟影响”区域中单击“查看用户”。  
    
    **注意**：由于你可以同时运行多个鱼叉式网络钓鱼模拟活动，因此你可以为不同的用户和组创建不同的模拟。  这些不同的模拟可能具有更适合不同用户的诱发因素。
    
4. 在用户列表中，选择“导出”以导出鱼叉式网络钓鱼攻击的受害者用户列表。
 

# <a name="end-of-lab"></a>实验室结束。
