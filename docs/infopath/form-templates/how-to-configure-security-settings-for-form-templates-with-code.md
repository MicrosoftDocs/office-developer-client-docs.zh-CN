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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300156"
---
# <a name="configure-security-settings-for-form-templates-with-code"></a><span data-ttu-id="80ca1-104">为包含代码的表单模板配置安全设置</span><span class="sxs-lookup"><span data-stu-id="80ca1-104">Configure Security Settings for Form Templates with Code</span></span>

<span data-ttu-id="80ca1-105">可以通过使用 .NET 配置管理单元自定义应用于 InfoPath 托管代码表单模板的权限集。</span><span class="sxs-lookup"><span data-stu-id="80ca1-105">You can customize the permission set that is applied to an InfoPath managed code form template by using the .NET Configuration snap-in.</span></span>
  
<span data-ttu-id="80ca1-p101">由 InfoPath 承载的公共语言运行时 (CLR) 将在计算机策略级别查找位于 All_Code 组下的名为  *InfoPath 表单模板*  的预定义代码组。CLR 将在该组下定义的权限集应用于运行表单代码的应用程序域 (AppDomain)。这样，您便可以自定义授予 InfoPath 托管代码表单模板的权限集。例如，您可以为从 https://MySite 下载的表单模板授予访问 Active Directory 的权限。</span><span class="sxs-lookup"><span data-stu-id="80ca1-p101">The common language runtime (CLR) hosted by InfoPath will look for a predefined code group named  *InfoPath Form Templates*  at the Machine policy level under the All_Code group. The CLR will apply the permission sets that are defined under that group to the application domain (AppDomain) where the form code runs. This enables you to customize the permission sets that are granted to InfoPath managed code form templates. For example, you can grant a form template downloaded from https://MySite permission to access the Active Directory.</span></span> 
  
<span data-ttu-id="80ca1-110">若要应用使用 .NET 配置管理单元定义的自定义安全策略，必须在将运行该表单模板的所有客户端计算机上部署该策略。</span><span class="sxs-lookup"><span data-stu-id="80ca1-110">For custom security policy defined by using the .NET Configuration snap-in to be applied, it must be deployed on all the client computers where the form template will run.</span></span>
  
<span data-ttu-id="80ca1-111">有关 InfoPath 托管代码表单模板的安全模型的详细信息，请参阅[关于具有代码的表单模板的安全模型](about-the-security-model-for-form-templates-with-code.md)</span><span class="sxs-lookup"><span data-stu-id="80ca1-111">For more information about the security model for InfoPath managed code form templates, see [About the Security Model for Form Templates with Code](about-the-security-model-for-form-templates-with-code.md)</span></span>
  
## <a name="creating-a-code-group-for-infopath-form-templates"></a><span data-ttu-id="80ca1-112">为 InfoPath 表单模板创建一个代码组</span><span class="sxs-lookup"><span data-stu-id="80ca1-112">Creating a Code Group for InfoPath Form Templates</span></span>

<span data-ttu-id="80ca1-p102">以下过程将创建一个未对 InfoPath 托管代码表单模板（在本地计算机上安装或注册的表单模板除外）授予权限的代码组，在该代码组下，您可以为位于特定 URL 或 UNC 的 InfoPath 表单模板指定权限集。有关如何为  `InfoPath Form Templates`代码组内的代码组创建和指定权限集的信息，请参阅以下过程。</span><span class="sxs-lookup"><span data-stu-id="80ca1-p102">The following procedure will create a code group that grants no permissions to InfoPath managed code form templates (except those that are installed or registered on your local computer) under which you can assign permission sets to InfoPath form templates located at specific URLs or UNCs. For information about how to create and assign permission sets to code groups within the  `InfoPath Form Templates` code group, see the following procedure.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="80ca1-115">与随同 Microsoft .NET Framework 1.1 可分发软件包一起安装的 **Microsoft .NET Framework 1.1 Configuration** 工具不同，**Microsoft .NET Framework 2.0 Configuration** 仅随 Microsoft .NET Framework 2.0 软件开发工具包一起安装。</span><span class="sxs-lookup"><span data-stu-id="80ca1-115">Unlike the **Microsoft .NET Framework 1.1 Configuration** tool that is installed with the Microsoft .NET Framework 1.1 Redistributable Package, the **Microsoft .NET Framework 2.0 Configuration** is installed only with the Microsoft .NET Framework 2.0 Software Development Kit (SDK).</span></span> 
  
### <a name="to-create-a-custom-security-code-group-for-infopath-managed-code-forms"></a><span data-ttu-id="80ca1-116">为 InfoPath 托管代码表单创建自定义安全代码组</span><span class="sxs-lookup"><span data-stu-id="80ca1-116">To create a custom security code group for InfoPath managed code forms</span></span>

1. <span data-ttu-id="80ca1-117">在 **"开始"** 菜单中，指向 **"管理工具"**，然后单击 **"Microsoft .NET Framework 2.0 Configuration"**。</span><span class="sxs-lookup"><span data-stu-id="80ca1-117">From the **Start** menu, point to **Administrative Tools**, and then click **Microsoft .NET Framework 2.0 Configuration**.</span></span>
    
    <span data-ttu-id="80ca1-118">如果“开始”菜单上没有“管理工具”，请在“控制面板”中打开“管理工具”，然后双击“Microsoft .NET Framework 2.0 Configuration”。</span><span class="sxs-lookup"><span data-stu-id="80ca1-118">If you do not have **Administrative Tools** on the **Start** menu, from the **Control Panel** open **Administrative Tools**, and then double-click **Microsoft .NET Framework 2.0 Configuration**.</span></span>
    
2. <span data-ttu-id="80ca1-119">在 **"我的电脑"** 下，展开 **"运行库安全策略"** 节点、 **"计算机"** 节点、 **"代码组"** 节点、 **"All_Code"** 节点，然后右键单击 **"All_Code"** 节点并单击 **"新建"** 以打开 **"创建代码组"** 对话框。</span><span class="sxs-lookup"><span data-stu-id="80ca1-119">Under **My Computer**, expand the **Runtime Security Policy** node, the **Machine** node, **Code Groups** node, the **All_Code** node, and then right-click the **All_Code** node and click **New** to open the **Create Code Group** dialog box.</span></span> 
    
3. <span data-ttu-id="80ca1-120">将新建代码组命名为  `InfoPath Form Templates`（这些文本必须完全正确），然后单击 **"下一步"**。</span><span class="sxs-lookup"><span data-stu-id="80ca1-120">Name the new code group  `InfoPath Form Templates` (this text must be exact), and then click **Next**.</span></span>
    
4. <span data-ttu-id="80ca1-121">将代码组的条件类型设置为 **"所有代码"**，然后单击 **"下一步"**。</span><span class="sxs-lookup"><span data-stu-id="80ca1-121">Set the condition type for the code group to **All Code**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="80ca1-122">单击 **"使用现有权限集"**，为代码组指定 **"无"** 权限集，再单击 **"下一步"**，然后单击 **"完成"**。</span><span class="sxs-lookup"><span data-stu-id="80ca1-122">Click **Use existing permission set**, assign the **Nothing** permission set to the code group, click **Next**, and then click **Finish**.</span></span>
    
6. <span data-ttu-id="80ca1-123">若要应用新设置，请关闭并重新启动 InfoPath。</span><span class="sxs-lookup"><span data-stu-id="80ca1-123">To apply the new settings, close and restart InfoPath.</span></span>
    
<span data-ttu-id="80ca1-124">如果愿意，可以通过将“**无**”权限集以外的权限集指定给“**InfoPath Form Templates**”代码组，来管理所有 InfoPath 托管代码表单模板的权限集。</span><span class="sxs-lookup"><span data-stu-id="80ca1-124">If you prefer, you can manage the permission set for all InfoPath managed code form templates by assigning a permission set other than the **Nothing** permission set to the **InfoPath Form Templates** code group.</span></span> 
> [!NOTE]
> <span data-ttu-id="80ca1-p103">[!注释] 通过在 **".NET Configuration 2.0"** 管理单元中右键单击安全代码组，单击 **"属性"**，再单击 **"权限集"** 选项卡，您可以随时更改该组的权限集。</span><span class="sxs-lookup"><span data-stu-id="80ca1-p103">You can change the permission set for a security code group at any time by right-clicking the group in the . **NET Configuration 2.0** snap-in, clicking **Properties**, and then clicking the **Permission Set** tab.</span></span> 
  
## <a name="assigning-fulltrust-to-forms-at-a-specific-url-or-unc"></a><span data-ttu-id="80ca1-127">为位于特定 URL 或 UNC 的表单指定 FullTrust</span><span class="sxs-lookup"><span data-stu-id="80ca1-127">Assigning FullTrust to Forms at a Specific URL or UNC</span></span>

<span data-ttu-id="80ca1-p104">可以在“InfoPath 表单模板”组下创建代码组，以便为位于特定 URL 或 UNC 位置的表单模板授予完全信任权限集。执行该操作后，发布到指定位置的每个表单模板均以完全信任状态运行。</span><span class="sxs-lookup"><span data-stu-id="80ca1-p104">You can create code groups under the **InfoPath Form Templates** group to grant the full trust permission set to form templates from a particular URL or UNC location. After doing this, every form template published to the specified location will run fully trusted.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="80ca1-130">[!注释] 从本地计算机加载的表单模板（My Computer Zone 代码组）由 InfoPath 使用随机 URL 进行加载。</span><span class="sxs-lookup"><span data-stu-id="80ca1-130">A form template that is loaded from the local computer (My Computer Zone code group) is loaded by InfoPath using a random URL.</span></span> <span data-ttu-id="80ca1-131">因此，不能采用以下过程向此类表单模板授予 FullTrust 权限集。</span><span class="sxs-lookup"><span data-stu-id="80ca1-131">For this reason, you cannot use the following procedure to grant the FullTrust permission set to such a form template.</span></span> <span data-ttu-id="80ca1-132">要为本地安装的表单模板授予 FullTrust 权限集，请使用[部署包含代码的 InfoPath 表单模板](how-to-deploy-infopath-form-templates-with-code.md)主题的“部署需要‘完全信任’的表单模板”一节中介绍的过程之一。</span><span class="sxs-lookup"><span data-stu-id="80ca1-132">To grant a locally installed form template the FullTrust permission set, use one of the procedures that are described in the "Deploying Form Templates That Require Full Trust" section of the [Deploy InfoPath Form Templates with Code](how-to-deploy-infopath-form-templates-with-code.md) topic.</span></span> 
  
### <a name="to-assign-fulltrust-to-infopath-forms-at-a-specific-url-or-unc-location"></a><span data-ttu-id="80ca1-133">为位于特定 URL 或 UNC 位置的 InfoPath 表单指定 FullTrust</span><span class="sxs-lookup"><span data-stu-id="80ca1-133">To assign FullTrust to InfoPath forms at a specific URL or UNC location</span></span>

1. <span data-ttu-id="80ca1-134">在 **"开始"** 菜单中，指向 **"管理工具"**，然后单击 **"Microsoft .NET Framework 2.0 Configuration"**。</span><span class="sxs-lookup"><span data-stu-id="80ca1-134">From the **Start** menu, point to **Administrative Tools**, and then click **Microsoft .NET Framework 2.0 Configuration**.</span></span>
    
    <span data-ttu-id="80ca1-135">如果“开始”菜单上没有“管理工具”，请在“控制面板”中打开“管理工具”，然后双击“Microsoft .NET Framework 2.0 Configuration”。</span><span class="sxs-lookup"><span data-stu-id="80ca1-135">If you do not have **Administrative Tools** on the **Start** menu, from the **Control Panel** open **Administrative Tools**, and then double-click **Microsoft .NET Framework 2.0 Configuration**.</span></span>
    
2. <span data-ttu-id="80ca1-136">在 **"我的电脑"** 下，展开 **"运行库安全策略"** 节点、 **"计算机"** 节点、 **"代码组"** 节点、 **"All_Code"** 节点，然后单击 **"InfoPath 表单模板"** 节点。</span><span class="sxs-lookup"><span data-stu-id="80ca1-136">Under **My Computer**, expand the **Runtime Security Policy** node, the **Machine** node, **Code Groups** node, the **All_Code** node, and then click the **InfoPath Form Templates** node.</span></span> 
    
3. <span data-ttu-id="80ca1-137">在右侧窗格的 **"任务"** 列表中，单击 **"添加子代码组"**，命名该代码组，然后单击 **"下一步"**。</span><span class="sxs-lookup"><span data-stu-id="80ca1-137">In **Tasks** list in the right pane, click **Add a Child Code Group**, name the code group, and then click **Next**.</span></span>
    
4. <span data-ttu-id="80ca1-138">在“**选择此代码组的条件类型**”列表中，选择“**URL**”，然后输入要授予“**FullTrust**”权限集的 InfoPath 托管代码表单模板所在位置的 URL 或 UNC。</span><span class="sxs-lookup"><span data-stu-id="80ca1-138">In the **Choose the condition type for this code group** list, select **URL**, and then enter the URL or UNC for the location of the InfoPath managed code form templates that you want to grant the **FullTrust** permission set.</span></span> 
    
    <span data-ttu-id="80ca1-p106">若要限定将权限集指定给单个表单模板，请指定该特定表单模板的完整路径。例如：</span><span class="sxs-lookup"><span data-stu-id="80ca1-p106">To restrict the permission set to a single form template, specify the full path of that particular form template. For example:</span></span>
    
     `\\MyServer\MyShare\MyFormTemplate.xsn`
    
     `https://MySite/MySubsite/MyFormTempate.xsn`
    
    <span data-ttu-id="80ca1-p107">若要为某 URL 或 UNC 中的所有表单模板授予权限集，请省略模板的名称并在 URL 或 UNC 的末尾添加一个星号。例如：</span><span class="sxs-lookup"><span data-stu-id="80ca1-p107">To grant the permission set to all form templates in a URL or UNC, omit the name of the template and add an asterisk at the end of the URL or UNC. For example:</span></span>
    
     `\\MyServer\MyShare\*`
    
     `https://MySite/MySubsite/*`
    
5. <span data-ttu-id="80ca1-143">单击 **"下一步"**，再单击 **"使用现有权限集"** 并将 **"FullTrust"** 权限集指定给该代码组。</span><span class="sxs-lookup"><span data-stu-id="80ca1-143">Click **Next**, and then click **Use existing permission set** and assign the **FullTrust** permission set to the code group.</span></span> 
    
6. <span data-ttu-id="80ca1-144">单击 **"下一步"**，再单击 **"完成"**。</span><span class="sxs-lookup"><span data-stu-id="80ca1-144">Click **Next**, and then click **Finish**.</span></span>
    
7. <span data-ttu-id="80ca1-145">若要应用新设置，请关闭并重新启动 InfoPath。</span><span class="sxs-lookup"><span data-stu-id="80ca1-145">To apply the new settings, close and restart InfoPath.</span></span>
    
> [!NOTE]
> <span data-ttu-id="80ca1-146">若要应用更加严格或自定义的权限集，请选择合适选项，不要在第 4 步选择 **FullTrust**。</span><span class="sxs-lookup"><span data-stu-id="80ca1-146">To apply a more restrictive or custom permission set, select the appropriate option instead of **FullTrust** in step 4.</span></span> 
  
## <a name="creating-a-deployment-package-for-infopath-security-policy"></a><span data-ttu-id="80ca1-147">为 InfoPath 安全策略创建部署包</span><span class="sxs-lookup"><span data-stu-id="80ca1-147">Creating a Deployment Package for InfoPath Security Policy</span></span>

<span data-ttu-id="80ca1-148">为 InfoPath 托管表单模板定义自定义安全策略后，可以创建 Windows Installer 程序包 (.msi)，以便使用"组策略"或 Microsoft Systems Management Server 在用户的计算机上部署此安全策略。</span><span class="sxs-lookup"><span data-stu-id="80ca1-148">After defining custom security policy for InfoPath managed-form templates, you can create a Windows Installer Package (.msi) to deploy this security policy on users' computers by using Group Policy or Microsoft Systems Management Server.</span></span>
  
### <a name="to-create-a-deployment-package-for-custom-infopath-security-policy"></a><span data-ttu-id="80ca1-149">为自定义 InfoPath 安全策略创建部署包</span><span class="sxs-lookup"><span data-stu-id="80ca1-149">To create a deployment package for custom InfoPath security policy</span></span>

1. <span data-ttu-id="80ca1-150">在 **"开始"** 菜单中，指向 **"管理工具"**，然后单击 **"Microsoft .NET Framework 2.0 Configuration"**。</span><span class="sxs-lookup"><span data-stu-id="80ca1-150">From the **Start** menu, point to **Administrative Tools**, and then click **Microsoft .NET Framework 2.0 Configuration**.</span></span>
    
    <span data-ttu-id="80ca1-151">如果“开始”菜单上没有“管理工具”，请在“控制面板”中打开“管理工具”，然后双击“Microsoft .NET Framework 2.0 Configuration”。</span><span class="sxs-lookup"><span data-stu-id="80ca1-151">If you do not have **Administrative Tools** on the **Start** menu, from the **Control Panel** open **Administrative Tools**, and then double-click **Microsoft .NET Framework 2.0 Configuration**.</span></span>
    
2. <span data-ttu-id="80ca1-152">右键单击 **"运行库安全策略"**，再单击 **"创建部署包"**。</span><span class="sxs-lookup"><span data-stu-id="80ca1-152">Right-click **Runtime Security Policy**, and then click **Create Deployment Package**.</span></span>
    
3. <span data-ttu-id="80ca1-153">在“选择要部署的安全策略”下，单击“计算机”，指定 Windows Installer 程序包的文件夹和文件名，再单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="80ca1-153">Under **Select the security policy to deploy**, click **Machine**, specify the folder and file name for the Windows Installer Package, and then click **Next**.</span></span>
    
4. <span data-ttu-id="80ca1-154">单击 **"完成"** 以创建部署包。</span><span class="sxs-lookup"><span data-stu-id="80ca1-154">Click **Finish** to create the deployment package.</span></span> 
    
5. <span data-ttu-id="80ca1-155">若要了解如何使用 .NET Framework 配置工具，请在 Visual Studio 帮助或 MSDN 网站中搜索“.NET Framework 配置工具 (Mscorcfg.msc)”。</span><span class="sxs-lookup"><span data-stu-id="80ca1-155">For information about how to use the .NET Framework Configuration tool, search Visual Studio Help or the MSDN website for ".NET Framework Configuration Tool (Mscorcfg.msc)".</span></span>
    
## <a name="see-also"></a><span data-ttu-id="80ca1-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80ca1-156">See also</span></span>



[<span data-ttu-id="80ca1-157">关于包含代码的表单模板的安全模型</span><span class="sxs-lookup"><span data-stu-id="80ca1-157">About the Security Model for Form Templates with Code</span></span>](about-the-security-model-for-form-templates-with-code.md)

