---
title: 发布包含代码的表单
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: caafab24-6413-4731-813d-cba3ae9ea97e
description: 任何网站集管理员都可以直接从 InfoPath Designer 发布向导中将包含代码的表单发布到 SharePoint 上的表单库。代码将在沙盒环境中执行，以使恶意代码无法损害服务器。这称为发布沙盒解决方案或发布到 SharePoint 沙盒基础结构。
ms.openlocfilehash: f8f8a48ea6810b5331198f6ddc112b3bd38ab886
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428324"
---
# <a name="publishing-forms-with-code"></a><span data-ttu-id="78445-105">发布包含代码的表单</span><span class="sxs-lookup"><span data-stu-id="78445-105">Publishing Forms with Code</span></span>

<span data-ttu-id="78445-p102">任何网站集管理员都可以直接从 InfoPath Designer 发布向导中将包含代码的表单发布到 SharePoint 上的表单库。代码将在沙盒环境中执行，以使恶意代码无法损害服务器。这称为发布沙盒解决方案或发布到 SharePoint 沙盒基础结构。</span><span class="sxs-lookup"><span data-stu-id="78445-p102">Any site collection administrator can publish forms with code directly from the InfoPath Designer publishing wizard to a form library on SharePoint. The code is executed in a sandboxed environment so that malicious code cannot harm the server. This is referred to as publishing a sandboxed solution or publishing to the SharePoint sandbox infrastructure.</span></span>
  
<span data-ttu-id="78445-p103">InfoPath 2010 和 SharePoint Server 2010 也支持管理员部署的解决方案。表单设计人员将包含代码的表单发布到本地存储，SharePoint 服务器场管理员随后将审阅和上载这些表单。代码将被赋予完全信任，并可以结合需要提升的权限的功能（例如文件 IO）。</span><span class="sxs-lookup"><span data-stu-id="78445-p103">InfoPath 2010 and SharePoint Server 2010 also support administrator-deployed solutions. A form designer publishes forms with code to a local store which are later reviewed and uploaded by a SharePoint farm administrator. The code is given full trust, and can incorporate functionality requiring elevated privileges such as file IO.</span></span>
  
## <a name="comparing-sandboxed-and-administrator-approved-solutions"></a><span data-ttu-id="78445-112">比较沙盒解决方案和经管理员核准的解决方案</span><span class="sxs-lookup"><span data-stu-id="78445-112">Comparing Sandboxed and Administrator-approved Solutions</span></span>

<span data-ttu-id="78445-113">下表概述了发布沙盒解决方案和经管理员核准的解决方案之间的差异。</span><span class="sxs-lookup"><span data-stu-id="78445-113">The following table summarizes the differences between publishing sandboxed and administrator-approved solutions.</span></span> 
  
||<span data-ttu-id="78445-114">**沙盒解决方案**</span><span class="sxs-lookup"><span data-stu-id="78445-114">**Sandboxed Solutions**</span></span>|<span data-ttu-id="78445-115">**经管理员核准的解决方案**</span><span class="sxs-lookup"><span data-stu-id="78445-115">**Administrator-approved Solutions**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="78445-116">**所需的权限**</span><span class="sxs-lookup"><span data-stu-id="78445-116">**Permissions Required**</span></span> <br/> |<span data-ttu-id="78445-117">可由任何网站集管理员发布。</span><span class="sxs-lookup"><span data-stu-id="78445-117">Can be published by any site collection administrator.</span></span>  <br/> |<span data-ttu-id="78445-118">可由服务器场管理员部署。</span><span class="sxs-lookup"><span data-stu-id="78445-118">Can be deployed by a farm administrator.</span></span>  <br/> |
|<span data-ttu-id="78445-119">**Publishing**</span><span class="sxs-lookup"><span data-stu-id="78445-119">**Publishing**</span></span> <br/> |<span data-ttu-id="78445-120">可直接从 InfoPath 中发布。</span><span class="sxs-lookup"><span data-stu-id="78445-120">Can be published directly from InfoPath.</span></span>  <br/> |<span data-ttu-id="78445-121">可使用管理中心或 stsadm 命令行工具部署。</span><span class="sxs-lookup"><span data-stu-id="78445-121">Can be deployed using Central Administration or the stsadm command-line tool.</span></span>  <br/> |
|<span data-ttu-id="78445-122">**保护**</span><span class="sxs-lookup"><span data-stu-id="78445-122">**Protection**</span></span> <br/> |<span data-ttu-id="78445-p104">代码运行于沙盒环境中。这可帮助保护服务器免受恶意代码的损害。</span><span class="sxs-lookup"><span data-stu-id="78445-p104">Code is run in a sandboxed environment. This helps protect the server from malicious code.</span></span>  <br/> |<span data-ttu-id="78445-125">代码能够以完全信任方式运行，并访问服务器上的任何资源。</span><span class="sxs-lookup"><span data-stu-id="78445-125">Code can run with full trust and access any resource on the server.</span></span>  <br/> |
|<span data-ttu-id="78445-126">**建议的用途**</span><span class="sxs-lookup"><span data-stu-id="78445-126">**Recommended Use**</span></span> <br/> |<span data-ttu-id="78445-127">仅需要少量代码的表单。</span><span class="sxs-lookup"><span data-stu-id="78445-127">Forms that only require a small amount of code.</span></span>  <br/> |<span data-ttu-id="78445-128">包含多行代码的表单。</span><span class="sxs-lookup"><span data-stu-id="78445-128">Forms that contain many lines of code.</span></span>  <br/> |
   
### <a name="publishing-form-templates-as-sandboxed-solutions"></a><span data-ttu-id="78445-129">以沙盒解决方案的形式发布表单模板</span><span class="sxs-lookup"><span data-stu-id="78445-129">Publishing Form Templates as Sandboxed Solutions</span></span>

<span data-ttu-id="78445-p105">以 沙盒解决方案 形式发布包含代码的表单与将任何其他表单发布到文档库没有不同之处。只需照常使用发布向导，您的表单即会上载到服务器并将在沙盒中运行。</span><span class="sxs-lookup"><span data-stu-id="78445-p105">Publishing a form with code as a sandboxed solution is no different from publishing any other form to a document library. Just use the publishing wizard as usual and your form will be uploaded to the server and will operate in the sandbox.</span></span>
  
<span data-ttu-id="78445-132">请注意，以 沙盒解决方案 的形式部署表单有某些限制：</span><span class="sxs-lookup"><span data-stu-id="78445-132">Note that there are certain restrictions to deploying your form as a sandboxed solution:</span></span>
  
- <span data-ttu-id="78445-133">必须为 InfoPath 表单。</span><span class="sxs-lookup"><span data-stu-id="78445-133">Must be an InfoPath form.</span></span>
    
- <span data-ttu-id="78445-134">编程语言必须使用 C# 或 Visual Basic。</span><span class="sxs-lookup"><span data-stu-id="78445-134">Must use C# or Visual Basic as the programming language.</span></span>
    
- <span data-ttu-id="78445-135">无法提交到电子邮件数据连接。</span><span class="sxs-lookup"><span data-stu-id="78445-135">Cannot submit to email data connections.</span></span>
    
- <span data-ttu-id="78445-136">无法为部件与部件的连接提升属性。</span><span class="sxs-lookup"><span data-stu-id="78445-136">Cannot have properties promoted for part-to-part connections.</span></span>
    
- <span data-ttu-id="78445-137">不能有任何托管元数据控件或数据连接。</span><span class="sxs-lookup"><span data-stu-id="78445-137">Must not have any managed meta-data controls or data connections.</span></span>
    
<span data-ttu-id="78445-138">若要使网站集管理员能够在 Microsoft SharePoint Server 2010 或运行 Microsoft SharePoint Foundation 2010 的服务器上使用 沙盒解决方案，服务器场管理员必须启动 Windows SharePoint 用户代码服务。</span><span class="sxs-lookup"><span data-stu-id="78445-138">To enable site collection administrators to use sandboxed solutions on Microsoft SharePoint Server 2010 or a server that runs Microsoft SharePoint Foundation 2010, the farm administrator must start the Windows SharePoint User Code service.</span></span>
  
### <a name="to-start-the-windows-sharepoint-user-code-service"></a><span data-ttu-id="78445-139">启动 Windows SharePoint 用户代码服务</span><span class="sxs-lookup"><span data-stu-id="78445-139">To start the Windows SharePoint User Code service</span></span>

1. <span data-ttu-id="78445-140">打开管理中心。</span><span class="sxs-lookup"><span data-stu-id="78445-140">Open Central Administration.</span></span>
    
2. <span data-ttu-id="78445-141">在“**系统服务**”下，单击“**管理服务器上的服务**”。</span><span class="sxs-lookup"><span data-stu-id="78445-141">Under **System Services**, click **Manage services on server**.</span></span>
    
3. <span data-ttu-id="78445-142">开启 **Microsoft SharePoint Foundation 用户代码服务**。</span><span class="sxs-lookup"><span data-stu-id="78445-142">Start the **Microsoft SharePoint Foundation User Code Service**.</span></span>
    
### <a name="to-publish-a-sandboxed-solution"></a><span data-ttu-id="78445-143">发布沙盒解决方案</span><span class="sxs-lookup"><span data-stu-id="78445-143">To publish a sandboxed solution</span></span>

1. <span data-ttu-id="78445-144">在 InfoPath 设计器中打开表单模板。</span><span class="sxs-lookup"><span data-stu-id="78445-144">Open the form template in the InfoPath designer.</span></span>
    
2. <span data-ttu-id="78445-145">单击“**文件**”选项卡，然后单击 Backstage 的“**发布**”选项卡上的“**SharePoint Server**”。</span><span class="sxs-lookup"><span data-stu-id="78445-145">Click the **File** tab, and then click **SharePoint Server** on the **Publish** tab in the Backstage.</span></span> 
    
3. <span data-ttu-id="78445-146">输入要将内容发布到的 SharePoint 站点的 URL ，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="78445-146">Enter the URL of the SharePoint site to publish to, and then click **Next**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="78445-147">您必须是此网站上的网站集管理员才能以 沙盒解决方案 的形式发布此表单模板。</span><span class="sxs-lookup"><span data-stu-id="78445-147">You must be a site collection administrator on this site to publish this form template as a sandboxed solution.</span></span> 
  
4. <span data-ttu-id="78445-148">选择“表单库”，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="78445-148">Select **Form Library**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="78445-149">选择“新建表单库”，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="78445-149">Select **Create a new form library**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="78445-150">输入表单库的名称和描述，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="78445-150">Enter the name and descriptions for your form library, and then click **Next**.</span></span>
    
7. <span data-ttu-id="78445-151">单击“**发布**”。</span><span class="sxs-lookup"><span data-stu-id="78445-151">Click **Publish**.</span></span>
    
<span data-ttu-id="78445-152">有关对适合于以 沙盒解决方案 形式发布的表单模板的方案进行演示的示例解决方案，请参阅[示例沙盒解决方案](sample-sandboxed-solutions.md)。</span><span class="sxs-lookup"><span data-stu-id="78445-152">For example solutions that demonstrate scenarios that are appropriate for form templates published as sandboxed solutions, see [Sample Sandboxed Solutions](sample-sandboxed-solutions.md).</span></span>
  
### <a name="publishing-form-templates-as-administrator-deployed-solutions"></a><span data-ttu-id="78445-153">以管理员部署的解决方案的形式发布表单模板</span><span class="sxs-lookup"><span data-stu-id="78445-153">Publishing Form Templates as Administrator-Deployed Solutions</span></span>

<span data-ttu-id="78445-154">如果您的表单有多个数据连接、需要安全信任安全性或者您需要服务器场范围的模板，则建议以经管理员核准的模板的方式发布表单。</span><span class="sxs-lookup"><span data-stu-id="78445-154">Publishing your form as an administrator-approved template is recommended if your form has many data connections, if it requires full-trust security, or if you require a farm-wide template.</span></span>
  
<span data-ttu-id="78445-155">服务器场管理员必须先完成几个步骤，然后才能在 SharePoint 上使用管理员部署的解决方案，并且开发人员必须在管理员参与之前准备好该解决方案。</span><span class="sxs-lookup"><span data-stu-id="78445-155">There are several steps that a farm administrator must complete before an administrator-deployed solution is available on SharePoint, and you as the developer must prepare the solution before the administrator is engaged.</span></span>
  
<span data-ttu-id="78445-156">首先，如果您的表单将要以完全信任的形式部署，则您必须按以下过程中所述的方式设置安全级别。</span><span class="sxs-lookup"><span data-stu-id="78445-156">First, if your form is going to be deployed as full trust, you must set the security level as described in the following procedure.</span></span>
  
### <a name="to-set-the-security-level-of-a-form-template-to-full-trust"></a><span data-ttu-id="78445-157">将表单模板的安全级别设置为完全信任</span><span class="sxs-lookup"><span data-stu-id="78445-157">To set the security level of a form template to full trust</span></span>

1. <span data-ttu-id="78445-158">在 InfoPath 设计器中打开表单模板。</span><span class="sxs-lookup"><span data-stu-id="78445-158">Open the form template in the InfoPath designer.</span></span>
    
2. <span data-ttu-id="78445-159">单击“**文件**”选项卡，在“**信息**”选项卡上单击“**表单选项**”。</span><span class="sxs-lookup"><span data-stu-id="78445-159">Click the **File** tab, on the **Info** tab click **Form Options**.</span></span>
    
3. <span data-ttu-id="78445-160">单击“**安全和信任**”类别，然后清除“**自动确定安全级别**”复选框。</span><span class="sxs-lookup"><span data-stu-id="78445-160">Click the **Security and Trust** category, and then clear the **Automatically determine security level** check box.</span></span> 
    
4. <span data-ttu-id="78445-161">选择“**完全信任**”。</span><span class="sxs-lookup"><span data-stu-id="78445-161">Select **Full Trust**.</span></span>
    
<span data-ttu-id="78445-162">然后，通过使用以下过程发布表单，但要注意与标准发布过程有一些不同之处。</span><span class="sxs-lookup"><span data-stu-id="78445-162">Then, publish the form by using the following procedure, but be aware that there are some differences from a standard publishing procedure.</span></span>
  
### <a name="to-publish-an-administrator-deployed-solution"></a><span data-ttu-id="78445-163">发布管理员部署的解决方案</span><span class="sxs-lookup"><span data-stu-id="78445-163">To publish an administrator-deployed solution</span></span>

1. <span data-ttu-id="78445-164">在“**发布向导**”的第一页中，指定 SharePoint Server 2010 或 SharePoint Foundation 2010 站点的位置，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="78445-164">In the first page of the **Publishing Wizard**, specify the location of the SharePoint Server 2010 or SharePoint Foundation 2010 site, and then click **Next**.</span></span>
    
2. <span data-ttu-id="78445-p106">InfoPath will automatically select the **Administrator-approved form template** check box on the second page of the wizard. Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="78445-p106">InfoPath will automatically select the **Administrator-approved form template** check box on the second page of the wizard. Click **Next**.</span></span>
    
3. <span data-ttu-id="78445-p107">第三页是管理员部署的解决方案所特有的。请将表单发布到本地存储，而不要选择 SharePoint Server。SharePoint 管理员在管理员部署过程中将从此位置上载文件。</span><span class="sxs-lookup"><span data-stu-id="78445-p107">The third page is unique to administrator-deployed scenarios. Instead of selecting a SharePoint Server, publish the form to a local store. The SharePoint administrator will upload the file from this location during the administrator deployment process.</span></span>
    
4. <span data-ttu-id="78445-170">完成“**发布向导**”的其余页面。</span><span class="sxs-lookup"><span data-stu-id="78445-170">Complete the remaining pages of the **Publishing Wizard**.</span></span>
    

