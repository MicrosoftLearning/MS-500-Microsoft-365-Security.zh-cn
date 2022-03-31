---
ms.openlocfilehash: 3ca1e42c5a1cd994aa572748a257019f04a6093c
ms.sourcegitcommit: c203d5d5aaaf93bae4a8af2ae04b27f6314242c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "137820882"
---
# <a name="module-3---lab-2---exercise-3---activate-and-deactivate-pim-roles"></a>模块 3 - 实验室 2 - 练习 3 - 激活和停用 PIM 角色


### <a name="task-1-activate-a-role"></a>任务 1：
          激活角色


需要充当某个 Azure AD 目录角色时，可在 PIM 中使用“我的角色”导航选项来请求激活。


1.  在 Azure 门户中，以 Holly 的身份登录，单击“所有服务”，然后搜索并选择 `Azure AD Privileged Identity Management`。

     ![屏幕快照](../Media/a52510a3-b2a2-4b21-91a8-ee7f34b39a72.png)

1.  单击“Azure AD 角色”。
 
1.  单击“快速开始”，然后单击“分配资格”。

     ![屏幕快照](../Media/a7af9dbc-d901-4c9e-9cd5-63fd30726639.png)

1.  单击 `Billing Administrator` 并将 Patti Fernandez 重新添加到“计费管理员”角色。


1.  打开 InPrivate 浏览会话，然后导航到 `https://portal.azure.com` 并以 Patti 的身份使用她的 UPN 登录。  示例 PattiF@YourTenantHere.onmicrosoft.com 使用实验室宿主提供的密码（提示：密码可能与 MOD 管理员密码相同）。  

1.  在 Azure 门户中，单击“所有服务”，搜索并选择“Azure AD Privileged Identity Management” 。

     ![屏幕快照](../Media/a52510a3-b2a2-4b21-91a8-ee7f34b39a72.png)

1.  单击“Azure AD 角色”。

1.  单击“快速开始”，然后单击“激活你的角色” 。

1.  在“计费管理员”角色上，向右滚动并单击“激活”。

     ![屏幕快照](../Media/bd3d79a3-a66d-48a5-8b2e-94c18358b250.png)

1.  单击“先验证你的身份再继续”（如果其出现在此处）。 只需在每个会话中执行身份验证一次。 运行向导以对 Patti 进行身份验证。
 
1.  返回 Azure 门户后，单击“所有服务”，然后搜索并选择 `Azure AD Privileged Identity Management`。

1.  选择“Azure AD 角色”，然后在“快速启动”边栏选项卡上单击“激活你的角色” 。

1.  在“计费管理员”角色上，向右滚动并单击“激活”。

     ![屏幕快照](../Media/bd3d79a3-a66d-48a5-8b2e-94c18358b250.png)

1.  输入激活原因，然后单击“激活”

     ![屏幕快照](../Media/b17f972d-8df2-4b78-a361-202bab94dd17.png)

默认情况下，除非在设置中显式配置，否则角色无需批准。 

 如果角色不需要审批，则会激活该角色并将其添加到活动角色列表中。 若要立即使用该角色，请按照下一部分中的步骤操作。

 如果角色需要审批才能激活，则浏览器右上角会显示一条通知，告知你请求正在等待审批。


### <a name="task-2-use-a-role-immediately-after-activation"></a>任务 2：激活后立即使用角色


在 PIM 中激活角色时，最多可能需要 10 分钟才能访问管理门户或在特定管理工作内执行功能。 若要强制更新权限，请使用“应用程序访问”页，如以下步骤所述。


1.  单击“注销”。

1.  在 inPrivate 浏览会话中以 Patti 的身份重新登录。


### <a name="task-3-view-the-status-of-your-requests"></a>任务 3：查看你的请求状态


可以查看等待激活的请求的状态。


1.  仍然以 Patti 的身份登录，在 Azure 门户中，单击“所有服务”，然后搜索并选择 `Azure AD Privileged Identity Management`。 

1.  单击“Azure AD 角色”。

1.  单击“待处理请求”，查看你的请求列表。


### <a name="task-4-deactivate-a-role"></a>任务 4：停用角色


角色激活后，在达到时间限制（符合条件的时间段）时会自动停用。

如果提前完成了管理员任务，也可以在 Azure AD Privileged Identity Management 中手动停用角色。



1.  仍以“Patti”的身份登录，打开 Azure AD Privileged Identity Management。

1.  单击“Azure AD 角色”。

1.  单击“我的角色”。

     ![屏幕快照](../Media/72435386-92e6-4cb7-9107-7adcc1198389.png)

1.  单击“活动分配”，查看活动角色列表。

1.  找到已用完的角色，然后单击“停用”。

     ![屏幕快照](../Media/6360dbed-ceea-4139-8282-a95f2b26ebd2.png)

1.  再次单击“停用”。

     ![屏幕快照](../Media/deactivate.png)




# <a name="continue-to-exercise-4"></a>继续进行练习 4
