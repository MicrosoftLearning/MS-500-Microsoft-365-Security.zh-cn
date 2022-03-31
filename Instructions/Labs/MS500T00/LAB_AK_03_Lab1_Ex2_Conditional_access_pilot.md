---
ms.openlocfilehash: 122bdaf3d5a1dbd026c22458869ac41fc06d4380
ms.sourcegitcommit: 25b9793190d40e69ed31815267fb6754397768bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "137943329"
---
# <a name="module-3---lab-1---exercise-2----mfa-conditional-access-complete-an-azure-multi-factor-authentication-pilot-roll-out"></a>模块 3 - 实验室 1 - 练习 2 - MFA 条件访问（完成 Azure 多重身份验证试点发布）


在本练习中，你将配置条件访问策略，在登录到 Azure 门户时启用 Azure 多重身份验证 (Azure MFA)。 此策略是针对特定的试点用户组进行部署和测试的。 与传统的强制方法相比，使用条件访问部署 Azure MFA 为组织和管理员提供了极大的灵活性。

- 启用 Azure 多重身份验证
- 测试 Azure 多重身份验证


### <a name="task-1-enable-azure-multi-factor-authentication"></a>任务 1：启用 Azure 多重身份验证

1.  返回到以全局管理员 Holly Dickson 的身份登录的 Azure 门户。

1.  在“中心”上，转到“Azure Active Directory”。

1.  单击“组”，然后单击“+ 新建组” 。

     ![屏幕快照](../Media/cb9c5324-cbb6-476e-9c7d-1920de301d40.png)

1.  输入以下信息，然后选择“创建”：

      * 组类型：`Security`
      * 组名：`MFA Pilot`
      * 组说明：`MFA Pilot Group`
      * 成员身份类型：`Assigned`
      * 成员：选择 `Lynne Robbins`
  
  
      ![屏幕快照](../Media/5457b62d-dc78-4043-bd72-3d7901bbcd71.png)
  
2.  浏览到“Azure Active Directory”，单击“安全”，然后在“策略”边栏选项卡上选择“条件访问”   。


3.  选择“+ 新建策略”，然后选择“创建新策略”。 


4.  将策略命名为 `MFA Pilot`
5.  在“用户或工作负载标识”下，单击“已选择 0 个用户或工作负载标识”。  选择“选择用户和组”单选按钮并选中“用户和组”框 。
    * 选择试点组 `MFA Pilot`
    * 单击“选择”

6.  在“云应用或操作”部分，单击“没有选择云应用、操作或身份验证上下文”。 
    * 单击“选择”。 Azure 门户的云应用是 `Microsoft Azure Management` 选择它。
    * 单击“选择应用”

7.  跳过“条件”部分
8.  在“授予”下的“访问控制”部分，单击“已选择 0 个控件”，并确保选中“授予访问权限”单选按钮。   
    * 选中“要求多重身份验证”复选框
    * 单击“选择”

9.  跳过“会话”部分
10. 将“启用策略”开关设置为“开”
11. 单击“创建” 

    **注意**：若策略失败，请检查工作，然后再次“创建”。 

### <a name="task-2-test-azure-multi-factor-authentication"></a>任务 2：测试 Azure 多重身份验证


为了证明条件访问策略正常工作，通过以下方式进行测试：登录到不要求 MFA 的某个资源，然后登录到要求 MFA 的 Azure 门户。


2.  在 InPrivate 或 incognito 模式下打开新的浏览器窗口并浏览到 **`https://portal.azure.com`**

       * 使用 Lynne Robbins 用户身份进行登录（Lynne 的密码可能与实验室托管服务提供商提供的 MOD 管理员密码相同），注意现在应注册并使用 Azure 多重身份验证。
       * 关闭浏览器窗口。



# <a name="end-of-lab"></a>实验室结束
