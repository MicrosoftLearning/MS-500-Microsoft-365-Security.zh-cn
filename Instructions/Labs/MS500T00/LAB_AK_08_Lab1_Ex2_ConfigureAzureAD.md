---
ms.openlocfilehash: 782446909eff9db7d21ab7e66db1d3c48628a9e9
ms.sourcegitcommit: 25b9793190d40e69ed31815267fb6754397768bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "137943263"
---
# <a name="module-8---lab-1---exercise-2---configure-azure-ad-for-intune"></a>模块 8 - 实验室 1 - 练习 2 - 为 Intune 配置 Azure AD 

在本练习中，你将激活 Intune 移动设备管理 (MDM) 的自动客户端注册。 这样你可以管理移动设备访问，并设置对设备的访问限制策略，除非采用某些操作，比如强密码和屏幕超时。

### <a name="task-1-integrate-azure-ad-with-intune"></a>任务 1：将 Azure AD 与 Intune 集成

1. 你仍应以 Admin 的身份登录到客户端 1 VM (LON-CL1)，并且应以 Holly Dickson 的身份登录到 Microsoft 365 。

2. 在 Azure 门户中，导航到 `https://portal.azure.com`，选择“所有服务”，搜索并选择“Azure Active Directory”。  

3. 在“Adatum Corporation - 概览”窗口，在“管理”下面的左侧窗格中，选择“移动性(MDM 和 MAM)”，然后在右侧的“详细信息”窗格中，选择“Microsoft Intune”   。

    **注意：** 如果看到自动注册仅适用于 Azure AD Premium 的通知，请按 F5 刷新 Web 浏览器中的页面，然后选择“Microsoft Intune”。

4. 在“配置”窗口的“MDM 用户范围”行，选择“全部”  。

    **注意：** 将此参数设置为“全部”即可允许将设备加入 Azure AD 的用户也自动注册到 Intune。

5. 选择“还原默认 MDM URL”可确保配置了正确的客户端注册 URL。

6. 在“配置”窗口顶部的菜单栏中，选择“保存” 。

7. 使 Azure 门户保持打开状态以进行下一个任务。

你现在已经配置了租户，所有的用户只要使用 Azure AD 帐户凭据登录到 Windows 10 客户端，即可将客户端注册到 Intune。


### <a name="task-2-configure-azure-ad-join"></a>任务 2：配置 Azure AD 联接

1. 在 Azure 门户的左侧导航窗格中，选择“Azure Active Directory” 。

2. 在“Adatum Corporation - 概览”窗口，在“管理”下的左侧部分，选择“设备”  。

3. 在左侧窗格中选择“所有设备”，在右侧的详细信息窗格中，确认未列出任何设备。 这是由于还没有任何设备加入 Azure Active Directory。

4. 在“设备 - 全部设备”窗口的左侧窗格中，选择“设备设置” 。

5. 在右侧的详细信息窗格中，“用户可以将设备加入 Azure AD”属性当前设置为“全部” 。 这表示所有 Azure AD 用户都可以将其设备加入 Azure Active Directory。 改为单击“已选择”。

6. 在此字段下的“已选择”部分，单击“未选中成员” 。

7. 在“允许加入设备的成员”窗口中，选择“+ 添加” 

8. 在右侧的“添加成员”窗格中，选择“Alex Wilber”，在屏幕底部选择“选择”，然后选择“确定”   。

9. 返回到右侧的“设备设置”详细信息窗格，向下滚动并验证“需要多重身份验证才能通过 Azure AD 注册或联接设备”设置为“否”。   “每个用户的最大设备数”属性当前设置为 50。  从下拉框中选择“10”。

10. 在详细信息窗格顶部的菜单栏中，选择“保存”。

11. 使 Azure 门户保持打开状态以进行下一个任务。

你已经更改了用户将设备加入 Azure AD 租户的默认设置。


### <a name="task-3-create-dynamic-azure-ad-device-group"></a>任务 3：创建动态 Azure AD 设备组

1. 在 Azure 门户的左侧导航窗格中，选择“Azure Active Directory” 。

2. 在“Adatum Corporation - 概览”窗口，在“管理”下的左侧部分，选择“组”  。

3. 在“组 - 所有组”窗口，在右侧详细信息窗格的菜单栏选择“+ 新建组” 。

4. 在“新建组”窗口中，输入以下信息：

    - 组类型：**安全**
    - 组名：`Enrolled Devices`
    - 成员身份类型：动态设备
    - 所有者：选择“未选择所有者”链接，然后在“添加所有者”窗口，选择 `Alex Wilber`，然后选择“选择”。  

5. 在“动态设备成员”下，单击“添加动态查询” 。

6. 在“动态成员资格规则”窗格中，为此表达式配置以下字段：

    - 属性：选择下拉箭头，并选择“managementType”。
    - 运算符：选择下拉箭头，并选择“等于”。  
    - 值：输入 `MDM`

3. 选择“规则语法”字段。 应该会显示以下规则：

    (device.managementType -eq &quot;MDM&quot;)

7. 在窗口顶部的菜单栏中，选择“保存”。

8. 在“新建组”窗口中，选择窗口底部的“创建”按钮 。

9. 现在组列表中应该会出现“已注册的设备”组。

10. 使 Azure 门户保持打开状态以进行下一个任务。


# <a name="proceed-to-exercise-3"></a>继续完成练习 3
