---
title: 为包含代码的表单模板配置安全设置
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- security policy deployment package [infopath 2007],URLs [InfoPath 2007], assigning FullTrust,code access security [InfoPath 2007],UNCs [InfoPath 2007], assigning FullTrust,CAS [InfoPath 2007],security [InfoPath 2007], configuring,code groups [InfoPath 2007],FullTrust [InfoPath 2007], assigning to UNCs,FullTrust [InfoPath 2007], assigning to URLs
localization_priority: Normal
ms.assetid: 24d1a322-581f-497e-b97b-bd02c4516551
description: 可以通过使用 .NET 配置管理单元自定义应用于 InfoPath 托管代码表单模板的权限集。
ms.openlocfilehash: 77f3546d976bb5ea353aa3fbe58ba7af6cd92a6d
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391414"
---
# <a name="configure-security-settings-for-form-templates-with-code"></a>为包含代码的表单模板配置安全设置

可以通过使用 .NET 配置管理单元自定义应用于 InfoPath 托管代码表单模板的权限集。
  
由 InfoPath 承载的公共语言运行时 (CLR) 将在计算机策略级别查找位于 All_Code 组下的名为  *InfoPath 表单模板*  的预定义代码组。CLR 将在该组下定义的权限集应用于运行表单代码的应用程序域 (AppDomain)。这样，您便可以自定义授予 InfoPath 托管代码表单模板的权限集。例如，您可以为从 https://MySite 下载的表单模板授予访问 Active Directory 的权限。 
  
若要应用使用 .NET 配置管理单元定义的自定义安全策略，必须在将运行该表单模板的所有客户端计算机上部署该策略。
  
有关 InfoPath 托管代码表单模板的安全模型的详细信息，请参阅[关于具有代码的表单模板的安全模型](about-the-security-model-for-form-templates-with-code.md)
  
## <a name="creating-a-code-group-for-infopath-form-templates"></a>为 InfoPath 表单模板创建一个代码组

以下过程将创建一个未对 InfoPath 托管代码表单模板（在本地计算机上安装或注册的表单模板除外）授予权限的代码组，在该代码组下，您可以为位于特定 URL 或 UNC 的 InfoPath 表单模板指定权限集。有关如何为  `InfoPath Form Templates`代码组内的代码组创建和指定权限集的信息，请参阅以下过程。 
  
> [!NOTE]
> 与随同 Microsoft .NET Framework 1.1 可分发软件包一起安装的 **Microsoft .NET Framework 1.1 Configuration** 工具不同，**Microsoft .NET Framework 2.0 Configuration** 仅随 Microsoft .NET Framework 2.0 软件开发工具包一起安装。 
  
### <a name="to-create-a-custom-security-code-group-for-infopath-managed-code-forms"></a>为 InfoPath 托管代码表单创建自定义安全代码组

1. 在 **"开始"** 菜单中，指向 **"管理工具"**，然后单击 **"Microsoft .NET Framework 2.0 Configuration"**。
    
    如果“开始”**** 菜单上没有“管理工具”****，请在“控制面板”**** 中打开“管理工具”****，然后双击“Microsoft .NET Framework 2.0 Configuration”****。
    
2. 在 **"我的电脑"** 下，展开 **"运行库安全策略"** 节点、 **"计算机"** 节点、 **"代码组"** 节点、 **"All_Code"** 节点，然后右键单击 **"All_Code"** 节点并单击 **"新建"** 以打开 **"创建代码组"** 对话框。 
    
3. 将新建代码组命名为  `InfoPath Form Templates`（这些文本必须完全正确），然后单击 **"下一步"**。
    
4. 将代码组的条件类型设置为 **"所有代码"**，然后单击 **"下一步"**。
    
5. 单击 **"使用现有权限集"**，为代码组指定 **"无"** 权限集，再单击 **"下一步"**，然后单击 **"完成"**。
    
6. 若要应用新设置，请关闭并重新启动 InfoPath。
    
如果愿意，可以通过将“**无**”权限集以外的权限集指定给“**InfoPath Form Templates**”代码组，来管理所有 InfoPath 托管代码表单模板的权限集。 
> [!NOTE]
> [!注释] 通过在 **".NET Configuration 2.0"** 管理单元中右键单击安全代码组，单击 **"属性"**，再单击 **"权限集"** 选项卡，您可以随时更改该组的权限集。 
  
## <a name="assigning-fulltrust-to-forms-at-a-specific-url-or-unc"></a>为位于特定 URL 或 UNC 的表单指定 FullTrust

可以在“InfoPath 表单模板”**** 组下创建代码组，以便为位于特定 URL 或 UNC 位置的表单模板授予完全信任权限集。执行该操作后，发布到指定位置的每个表单模板均以完全信任状态运行。 
  
> [!NOTE]
> [!注释] 从本地计算机加载的表单模板（My Computer Zone 代码组）由 InfoPath 使用随机 URL 进行加载。 因此，不能采用以下过程向此类表单模板授予 FullTrust 权限集。 要为本地安装的表单模板授予 FullTrust 权限集，请使用[部署包含代码的 InfoPath 表单模板](how-to-deploy-infopath-form-templates-with-code.md)主题的“部署需要‘完全信任’的表单模板”一节中介绍的过程之一。 
  
### <a name="to-assign-fulltrust-to-infopath-forms-at-a-specific-url-or-unc-location"></a>为位于特定 URL 或 UNC 位置的 InfoPath 表单指定 FullTrust

1. 在 **"开始"** 菜单中，指向 **"管理工具"**，然后单击 **"Microsoft .NET Framework 2.0 Configuration"**。
    
    如果“开始”**** 菜单上没有“管理工具”****，请在“控制面板”**** 中打开“管理工具”****，然后双击“Microsoft .NET Framework 2.0 Configuration”****。
    
2. 在 **"我的电脑"** 下，展开 **"运行库安全策略"** 节点、 **"计算机"** 节点、 **"代码组"** 节点、 **"All_Code"** 节点，然后单击 **"InfoPath 表单模板"** 节点。 
    
3. 在右侧窗格的 **"任务"** 列表中，单击 **"添加子代码组"**，命名该代码组，然后单击 **"下一步"**。
    
4. 在“**选择此代码组的条件类型**”列表中，选择“**URL**”，然后输入要授予“**FullTrust**”权限集的 InfoPath 托管代码表单模板所在位置的 URL 或 UNC。 
    
    若要限定将权限集指定给单个表单模板，请指定该特定表单模板的完整路径。例如：
    
     `\\MyServer\MyShare\MyFormTemplate.xsn`
    
     `https://MySite/MySubsite/MyFormTempate.xsn`
    
    若要为某 URL 或 UNC 中的所有表单模板授予权限集，请省略模板的名称并在 URL 或 UNC 的末尾添加一个星号。例如：
    
     `\\MyServer\MyShare\*`
    
     `https://MySite/MySubsite/*`
    
5. 单击 **"下一步"**，再单击 **"使用现有权限集"** 并将 **"FullTrust"** 权限集指定给该代码组。 
    
6. 单击 **"下一步"**，再单击 **"完成"**。
    
7. 若要应用新设置，请关闭并重新启动 InfoPath。
    
> [!NOTE]
> 若要应用更加严格或自定义的权限集，请选择合适选项，不要在第 4 步选择 **FullTrust**。 
  
## <a name="creating-a-deployment-package-for-infopath-security-policy"></a>为 InfoPath 安全策略创建部署包

为 InfoPath 托管表单模板定义自定义安全策略后，可以创建 Windows Installer 程序包 (.msi)，以便使用"组策略"或 Microsoft Systems Management Server 在用户的计算机上部署此安全策略。
  
### <a name="to-create-a-deployment-package-for-custom-infopath-security-policy"></a>为自定义 InfoPath 安全策略创建部署包

1. 在 **"开始"** 菜单中，指向 **"管理工具"**，然后单击 **"Microsoft .NET Framework 2.0 Configuration"**。
    
    如果“开始”**** 菜单上没有“管理工具”****，请在“控制面板”**** 中打开“管理工具”****，然后双击“Microsoft .NET Framework 2.0 Configuration”****。
    
2. 右键单击 **"运行库安全策略"**，再单击 **"创建部署包"**。
    
3. 在“选择要部署的安全策略”**** 下，单击“计算机”****，指定 Windows Installer 程序包的文件夹和文件名，再单击“下一步”****。
    
4. 单击 **"完成"** 以创建部署包。 
    
5. 若要了解如何使用 .NET Framework 配置工具，请在 Visual Studio 帮助或 MSDN 网站中搜索“.NET Framework 配置工具 (Mscorcfg.msc)”。
    
## <a name="see-also"></a>另请参阅



[关于包含代码的表单模板的安全模型](about-the-security-model-for-form-templates-with-code.md)

