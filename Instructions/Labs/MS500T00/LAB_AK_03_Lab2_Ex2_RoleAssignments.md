---
ms.openlocfilehash: 31718150ab2a0d5a4607e667b6936d7fd541ecdb
ms.sourcegitcommit: c203d5d5aaaf93bae4a8af2ae04b27f6314242c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "137820860"
---
# <a name="module-3---lab-2---exercise-2---assign-directory-roles"></a>模块 3 - 实验室 2 - 练习 2 - 分配目录角色


### <a name="task-1--make-a-user-eligible-for-a-role"></a>任务 1：确保用户有资格担任相关角色


在以下任务中，你将使用户有资格获得 Azure AD 目录角色。


1.  登录到 Azure 门户

1.  在 Azure 门户中，单击“所有服务”，然后搜索并选择 `Azure AD Privileged Identity Management`。

     ![屏幕快照](../Media/a52510a3-b2a2-4b21-91a8-ee7f34b39a72.png)

1.  选择“管理”下的“Azure AD 角色”，然后选择“管理”下的“角色”。   若此选项仍为灰色，可能需要刷新浏览器。

1.  选择 `Billing Administrator`。

1.  选择“+ 添加分配”以打开“选择成员”。 在“添加分配”屏幕中单击“未选择成员”。

1.  在“选择成员”屏幕中选择 `Patti Fernandez`，然后单击“选择”。 

1.  在“添加分配”屏幕中，单击“下一步”。 单击“分配”。  在分配窗口中查看添加的成员。

1.  分配角色后，选择的用户将显示在 **符合** 该角色条件的成员列表中。 


### <a name="task-2-make-a-role-assignment-permanent"></a>任务 2：将角色分配永久化


若要将某个角色分配设为永久，请执行以下步骤。



1.  在 Azure 门户中，单击“所有服务”，然后搜索并选择 `Azure AD Privileged Identity Management`。

     ![屏幕快照](../Media/a52510a3-b2a2-4b21-91a8-ee7f34b39a72.png)

1.  单击“Azure AD 角色”。

1.  单击“分配”。 
 
1.  单击“更新”将 Patti 更新为计费管理员，然后选中“永久合格”框 。  在成员资格设置中单击“保存”。

结果：现在，计费管理员现在被列为 Patti Fernandez 的永久角色。  换句话说，Patti 有提升为计费管理员角色的永久资格。


### <a name="task-3-remove-a-user-from-a-role"></a>任务 3：从角色中删除用户


可将用户从角色分配中删除，但始终必须至少保留一个永久的全局管理员用户。



1.  在 Azure 门户中，单击“所有服务”，然后搜索并选择 `Azure AD Privileged Identity Management`。

     ![屏幕快照](../Media/a52510a3-b2a2-4b21-91a8-ee7f34b39a72.png)

1.  单击“Azure AD 角色”。

1.  单击“分配”。 

1.  使用成员筛选器再次选择“Patti Fernandez”。
 
1.  在“符合条件的分配”下的“操作”区域中，单击“删除”。
 
1.  在要求确认的消息中，单击“是”。 将删除角色分配。


# <a name="continue-to-exercise-3"></a>继续进行练习 3
