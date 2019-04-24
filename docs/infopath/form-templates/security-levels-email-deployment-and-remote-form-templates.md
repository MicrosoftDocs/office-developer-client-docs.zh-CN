---
title: 安全级别、电子邮件部署和远程表单模板
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 7fc438ad-ae26-3632-3444-371537eaecb3
description: Microsoft InfoPath 支持将表单模板从一个位置移动到另一个位置, 以电子邮件附件的形式发送它们, 并创建已进行数字签名或已安装的完全信任表单模板。
ms.openlocfilehash: 799f2b19bfc4daa4a177d789a811d20ca09e7153
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299851"
---
# <a name="security-levels-email-deployment-and-remote-form-templates"></a><span data-ttu-id="ff18a-103">安全级别、电子邮件部署和远程表单模板</span><span class="sxs-lookup"><span data-stu-id="ff18a-103">Security levels, email deployment, and remote form templates</span></span>

<span data-ttu-id="ff18a-104">Microsoft InfoPath 支持将表单模板从一个位置移动到另一个位置, 以电子邮件附件的形式发送它们, 并创建已进行数字签名或已安装的完全信任表单模板。</span><span class="sxs-lookup"><span data-stu-id="ff18a-104">Microsoft InfoPath supports moving form templates from one location to another, sending them as an attachment to an email message, and creating Full Trust form templates that are digitally signed or installed.</span></span>
  
## <a name="security-levels"></a><span data-ttu-id="ff18a-105">安全级别</span><span class="sxs-lookup"><span data-stu-id="ff18a-105">Security levels</span></span>

<span data-ttu-id="ff18a-p101">表单模板可以具有三种不同安全级别中的一种，具体取决于表单所在的位置。以下各节分别介绍了这三种安全级别：</span><span class="sxs-lookup"><span data-stu-id="ff18a-p101">Form templates can have one of three security levels, depending on where the form is located. These three security levels are described in the following sections.</span></span> 
  
### <a name="restricted"></a><span data-ttu-id="ff18a-108">受限</span><span class="sxs-lookup"><span data-stu-id="ff18a-108">Restricted</span></span>

<span data-ttu-id="ff18a-p102">"受限"安全级别不允许在表单模板外部进行任何通信。此安全级别用于防止有害的表单将您计算机上的任何数据传输给恶意攻击者。在此安全模式下运行时，下列功能将不起作用：</span><span class="sxs-lookup"><span data-stu-id="ff18a-p102">The Restricted security level does not allow any communication outside the form template. This security level is intended to prevent harmful forms from transmitting any data from your computer to a malicious attacker. When running in this security mode, the following features will not work:</span></span>
  
- <span data-ttu-id="ff18a-112">HTML 任务窗格</span><span class="sxs-lookup"><span data-stu-id="ff18a-112">HTML Task Panes</span></span>  
- <span data-ttu-id="ff18a-113">SharePoint 查询</span><span class="sxs-lookup"><span data-stu-id="ff18a-113">SharePoint Query</span></span>
- <span data-ttu-id="ff18a-114">SharePoint 提交</span><span class="sxs-lookup"><span data-stu-id="ff18a-114">SharePoint Submit</span></span>
- <span data-ttu-id="ff18a-115">XML 文件查询</span><span class="sxs-lookup"><span data-stu-id="ff18a-115">XML File Query</span></span>
- <span data-ttu-id="ff18a-116">数据库查询</span><span class="sxs-lookup"><span data-stu-id="ff18a-116">Database Query</span></span>
- <span data-ttu-id="ff18a-117">数据库提交</span><span class="sxs-lookup"><span data-stu-id="ff18a-117">Database Submit</span></span>
- <span data-ttu-id="ff18a-118">Web 服务查询</span><span class="sxs-lookup"><span data-stu-id="ff18a-118">Web Service Query</span></span>
- <span data-ttu-id="ff18a-119">Web 服务提交</span><span class="sxs-lookup"><span data-stu-id="ff18a-119">Web Service Submit</span></span>
- <span data-ttu-id="ff18a-120">自定义代码提交</span><span class="sxs-lookup"><span data-stu-id="ff18a-120">Custom Code Submit</span></span>
- <span data-ttu-id="ff18a-121">宿主环境提交</span><span class="sxs-lookup"><span data-stu-id="ff18a-121">Hosting Environment Submit</span></span>
- <span data-ttu-id="ff18a-122">ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="ff18a-122">ActiveX Controls</span></span>
- <span data-ttu-id="ff18a-123">角色</span><span class="sxs-lookup"><span data-stu-id="ff18a-123">Roles</span></span>
- <span data-ttu-id="ff18a-124">SharePoint 工作流</span><span class="sxs-lookup"><span data-stu-id="ff18a-124">SharePoint Workflow</span></span>
- <span data-ttu-id="ff18a-125">打开新文档的规则</span><span class="sxs-lookup"><span data-stu-id="ff18a-125">Rules that open a New Document</span></span>
- <span data-ttu-id="ff18a-126">托管代码</span><span class="sxs-lookup"><span data-stu-id="ff18a-126">Managed Code</span></span>
- <span data-ttu-id="ff18a-127">外部打印视图</span><span class="sxs-lookup"><span data-stu-id="ff18a-127">External Print View</span></span>
- <span data-ttu-id="ff18a-128">链接图像</span><span class="sxs-lookup"><span data-stu-id="ff18a-128">Linked Images</span></span>
    
### <a name="domain"></a><span data-ttu-id="ff18a-129">域</span><span class="sxs-lookup"><span data-stu-id="ff18a-129">Domain</span></span>

<span data-ttu-id="ff18a-p103">“域”安全级别将表单操作限制在特定的 Internet 域中，将表单权限限制为只能进行该域所在的区域的 Internet Explorer 设置。允许表单与其所在域中的其他数据源进行通信，但通常不允许它从其他域检索数据，除非相应区域允许进行跨域通信。对于浏览器兼容的表单模板，这是所允许的最低安全级别。</span><span class="sxs-lookup"><span data-stu-id="ff18a-p103">The Domain security level restricts a form to a particular Internet domain and its permissions are restricted to the Internet Explorer settings for the zone where the domain is located. The form is allowed to communicate with other data sources inside its own domain but is typically not allowed to retrieve data from other domains unless the zone allows cross-domain communication. This is the minimum security level allowed for browser-compatible form templates.</span></span>
  
### <a name="full-trust"></a><span data-ttu-id="ff18a-133">完全信任</span><span class="sxs-lookup"><span data-stu-id="ff18a-133">Full Trust</span></span>

<span data-ttu-id="ff18a-p104">通过"完全信任"安全级别，您可以在将使用表单的计算机上以完全信任方式运行该表单。仅当您使用位于服务器上的表单，并且该表单的签名与您计算机上受信任根的发布者相符时，或者只有在安装表单时，才能使用这一安全级别。这两种方法均需要将 **requireFullTrust** 属性设置为"yes"。使用该设置时，表单可以访问对象模型调用（如文件保存），并且在以更严格的安全级别运行时所出现的某些安全提示将被禁用。</span><span class="sxs-lookup"><span data-stu-id="ff18a-p104">The Full Trust security level allows you to run a form with full trust on the computer where the form will be used. This security level can only be used when you are working with a form located on a server that is signed with a signature that matches a trusted root publisher on your computer, or by installing the form. Both methods require setting the **requireFullTrust** attribute to "yes". By using this setting, the form can access object model calls such as file save, and certain security prompts that appear when you run at a more restrictive security level are disabled.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ff18a-p105">[!注释] 在 InfoPath Designer 中生成的所有表单都具有与其相关的安全级别。InfoPath 会在其相关的安全级别下打开表单。如果与表单相关的安全级别高于可以授予该表单的安全级别，则表单将不会打开。</span><span class="sxs-lookup"><span data-stu-id="ff18a-p105">All forms generated in the InfoPath designer have a security level associated with them. InfoPath opens forms at their associated security level. If the security level associated with the form is higher than the security level that can be granted to it, the form will not open.</span></span> 
  
<span data-ttu-id="ff18a-p106">只能为已安装或已签名的表单模板设置"完全信任"安全级别；其他情况下的最高信任级别是"域"。InfoPath 不会自动将安全级别设置为"完全信任"。</span><span class="sxs-lookup"><span data-stu-id="ff18a-p106">The Full Trust security level can only be set for installed or signed form templates; otherwise, the maximum trust level is Domain. InfoPath will not set a security level to Full Trust automatically.</span></span>
  
<span data-ttu-id="ff18a-143">表单的安全级别是基于它的打开位置而授予的。</span><span class="sxs-lookup"><span data-stu-id="ff18a-143">Forms are granted security levels based on the location from which the form is opened.</span></span>
  
## <a name="trust-levels"></a><span data-ttu-id="ff18a-144">信任级别</span><span class="sxs-lookup"><span data-stu-id="ff18a-144">Trust levels</span></span>

<span data-ttu-id="ff18a-145">可授予表单模板的最高信任级别由"打开位置"和其他验证代码决定（如下表中所述）。</span><span class="sxs-lookup"><span data-stu-id="ff18a-145">The highest level of trust that can be granted to a form template is determined by the Opened From location and other verification code, as described in the following table.</span></span> <span data-ttu-id="ff18a-146">表中列出的属性 (例如, HTTP、UNC、 *requireFullTrust*) 是用于确定可以向表单授予的信任级别的条目, 并适用于在 InfoPath 客户端中打开的表单。</span><span class="sxs-lookup"><span data-stu-id="ff18a-146">The attributes listed in the table (for example, HTTP, UNC,  *requireFullTrust*) are entries that are used to determine the level of trust that can be granted to a form, and apply to forms opened in the InfoPath client.</span></span> 
  
|<span data-ttu-id="ff18a-147">授予的最高信任级别</span><span class="sxs-lookup"><span data-stu-id="ff18a-147">Highest Level of Trust Granted</span></span>|<span data-ttu-id="ff18a-148">完全信任</span><span class="sxs-lookup"><span data-stu-id="ff18a-148">Full Trust</span></span>|<span data-ttu-id="ff18a-149">客户端计算机（沙盒安全机制）</span><span class="sxs-lookup"><span data-stu-id="ff18a-149">Client Computer (Sandboxed)</span></span>|<span data-ttu-id="ff18a-150">Intranet（沙盒安全机制）</span><span class="sxs-lookup"><span data-stu-id="ff18a-150">Intranet (Sandboxed)</span></span>|<span data-ttu-id="ff18a-151">Internet（沙盒安全机制）</span><span class="sxs-lookup"><span data-stu-id="ff18a-151">Internet (Sandboxed)</span></span>|<span data-ttu-id="ff18a-152">受限</span><span class="sxs-lookup"><span data-stu-id="ff18a-152">Restricted</span></span>|
|:-----|:-----:|:-----:|:-----:|:-----:|:-----:|
|<span data-ttu-id="ff18a-153">**文件：访问路径=打开位置**</span><span class="sxs-lookup"><span data-stu-id="ff18a-153">**file: Access Path=Opened From Location**</span></span> <br/> |||<span data-ttu-id="ff18a-154">X</span><span class="sxs-lookup"><span data-stu-id="ff18a-154">X</span></span>  <br/> |||
|<span data-ttu-id="ff18a-155">**文件：访问路径\<\>打开位置或无访问路径（无论表单位于何处）**</span><span class="sxs-lookup"><span data-stu-id="ff18a-155">**file: Access Path\<\>Opened From Location or no Access Path (regardless of where the form came from)**</span></span> <br/> |||||<span data-ttu-id="ff18a-156">X</span><span class="sxs-lookup"><span data-stu-id="ff18a-156">X</span></span>  <br/> |
|<span data-ttu-id="ff18a-157">**打开位置：Intranet HTTP 或 HTTPS**</span><span class="sxs-lookup"><span data-stu-id="ff18a-157">**Opened From Location: Intranet HTTP or HTTPS**</span></span> <br/> |||<span data-ttu-id="ff18a-158">X</span><span class="sxs-lookup"><span data-stu-id="ff18a-158">X</span></span>  <br/> |||
|<span data-ttu-id="ff18a-159">**打开位置：Internet HTTP 或 HTTPS**</span><span class="sxs-lookup"><span data-stu-id="ff18a-159">**Opened From Location: Internet HTTP or HTTPS**</span></span> <br/> ||||<span data-ttu-id="ff18a-160">X</span><span class="sxs-lookup"><span data-stu-id="ff18a-160">X</span></span>  <br/> ||
|<span data-ttu-id="ff18a-161">**打开位置：UNC**</span><span class="sxs-lookup"><span data-stu-id="ff18a-161">**Opened From Location: UNC**</span></span> <br/> |||<span data-ttu-id="ff18a-162">X</span><span class="sxs-lookup"><span data-stu-id="ff18a-162">X</span></span>  <br/> |||
|<span data-ttu-id="ff18a-163">**安装的模板 (requireFullTrust="yes")**</span><span class="sxs-lookup"><span data-stu-id="ff18a-163">**Installed Template (requireFullTrust="yes")**</span></span> <br/> |<span data-ttu-id="ff18a-164">X</span><span class="sxs-lookup"><span data-stu-id="ff18a-164">X</span></span>  <br/> |||||
|<span data-ttu-id="ff18a-165">**安装的模板 (requireFullTrust="no")**</span><span class="sxs-lookup"><span data-stu-id="ff18a-165">**Installed Template (requireFullTrust="no")**</span></span> <br/> ||<span data-ttu-id="ff18a-166">X</span><span class="sxs-lookup"><span data-stu-id="ff18a-166">X</span></span>  <br/> ||||
|<span data-ttu-id="ff18a-167">**具有受信任发布者证书的模板**</span><span class="sxs-lookup"><span data-stu-id="ff18a-167">**Template with trusted publisher certificate**</span></span> <br/> |<span data-ttu-id="ff18a-168">X</span><span class="sxs-lookup"><span data-stu-id="ff18a-168">X</span></span>  <br/> |||||
|<span data-ttu-id="ff18a-169">**导出的表单文件**</span><span class="sxs-lookup"><span data-stu-id="ff18a-169">**Exported Form Files**</span></span> <br/> |||<span data-ttu-id="ff18a-170">X</span><span class="sxs-lookup"><span data-stu-id="ff18a-170">X</span></span>  <br/> |||
   
## <a name="form-open-behavior"></a><span data-ttu-id="ff18a-171">表单打开行为</span><span class="sxs-lookup"><span data-stu-id="ff18a-171">Form open behavior</span></span>

<span data-ttu-id="ff18a-p108">在 InfoPath 编辑器中打开的所有表单文件都受一组条件的约束，这些条件将决定表单在哪种安全级别打开以及是否打开。在编辑器中打开某 InfoPath 表单时，将使用相应的安全级别，否则将无法加载该表单。如果表单请求的安全级别高于可以授予它的安全级别（表单可以使用 **trustLevel** 或 **requireFullTrust** 属性来请求特定安全级别），系统将不允许加载该表单。另外，也可能以该表单所请求的安全级别加载它。如果不允许以请求的安全级别来打开表单模板，则用户将无法打开该表单并将收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="ff18a-p108">All form files opened in the InfoPath editor are bound by a set of conditions that determine the security level at which the form will open and whether it will open. When an InfoPath form is opened in the editor, it will be either opened with an appropriate security level, or it will not load. If a form requests a higher security level than it can be granted (a form can request a specific security level using the **trustLevel** or **requireFullTrust** attribute), it will not be allowed to load. Otherwise, it will be loaded with the security level it requests. If the form template is not allowed to open with the requested security level, the user will not be able to open the form and will receive an error message.</span></span> 
  
<span data-ttu-id="ff18a-177">下表描述在各个安全级别下打开表单时所需的条件，以及用户尝试打开表单时所出现的相关情况。</span><span class="sxs-lookup"><span data-stu-id="ff18a-177">The following table describes the conditions required for opening a form at each security level and the resultant behavior when the user attempts to open the form.</span></span>
  
|<span data-ttu-id="ff18a-178">编辑器打开/失败</span><span class="sxs-lookup"><span data-stu-id="ff18a-178">Editor Opens/Fails</span></span>|<span data-ttu-id="ff18a-179">完全信任 (requireFullTrust="yes")</span><span class="sxs-lookup"><span data-stu-id="ff18a-179">Full Trust (requireFullTrust="yes")</span></span>|<span data-ttu-id="ff18a-180">域信任（trustLevel="Domain" 或空白）</span><span class="sxs-lookup"><span data-stu-id="ff18a-180">Domain Trust (trustLevel="Domain" or blank)</span></span>|<span data-ttu-id="ff18a-181">受限 (trustLevel="Restricted")</span><span class="sxs-lookup"><span data-stu-id="ff18a-181">Restricted (trustLevel="Restricted")</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ff18a-182">**受信任（安装的或受信任的证书）**</span><span class="sxs-lookup"><span data-stu-id="ff18a-182">**Trusted (installed or trusted certificate)**</span></span> <br/> |<span data-ttu-id="ff18a-183">在"完全信任"级别打开编辑器</span><span class="sxs-lookup"><span data-stu-id="ff18a-183">Editor opens at Full Trust level</span></span>  <br/> |<span data-ttu-id="ff18a-184">不适用</span><span class="sxs-lookup"><span data-stu-id="ff18a-184">N/A</span></span>  <br/> |<span data-ttu-id="ff18a-185">不适用</span><span class="sxs-lookup"><span data-stu-id="ff18a-185">N/A</span></span>  <br/> |
|<span data-ttu-id="ff18a-186">**域信任：客户端计算机**</span><span class="sxs-lookup"><span data-stu-id="ff18a-186">**Domain Trust: Client Computer**</span></span> <br/> |<span data-ttu-id="ff18a-187">无法打开</span><span class="sxs-lookup"><span data-stu-id="ff18a-187">Fails to open</span></span>  <br/> |<span data-ttu-id="ff18a-188">在"域"级别打开编辑器</span><span class="sxs-lookup"><span data-stu-id="ff18a-188">Editor opens at Domain level</span></span>  <br/> |<span data-ttu-id="ff18a-189">在"受限"级别打开编辑器</span><span class="sxs-lookup"><span data-stu-id="ff18a-189">Editor opens at Restricted level</span></span>  <br/> |
|<span data-ttu-id="ff18a-190">**域信任：Intranet**</span><span class="sxs-lookup"><span data-stu-id="ff18a-190">**Domain Trust: Intranet**</span></span> <br/> |<span data-ttu-id="ff18a-191">无法打开</span><span class="sxs-lookup"><span data-stu-id="ff18a-191">Fails to open</span></span>  <br/> |<span data-ttu-id="ff18a-192">在"域"级别打开编辑器</span><span class="sxs-lookup"><span data-stu-id="ff18a-192">Editor opens at Domain level</span></span>  <br/> |<span data-ttu-id="ff18a-193">在"受限"级别打开编辑器</span><span class="sxs-lookup"><span data-stu-id="ff18a-193">Editor opens at Restricted level</span></span>  <br/> |
|<span data-ttu-id="ff18a-194">**域信任：Internet**</span><span class="sxs-lookup"><span data-stu-id="ff18a-194">**Domain Trust: Internet**</span></span> <br/> |<span data-ttu-id="ff18a-195">无法打开</span><span class="sxs-lookup"><span data-stu-id="ff18a-195">Fails to open</span></span>  <br/> |<span data-ttu-id="ff18a-196">在"域"级别打开编辑器</span><span class="sxs-lookup"><span data-stu-id="ff18a-196">Editor opens at Domain level</span></span>  <br/> |<span data-ttu-id="ff18a-197">在"受限"级别打开编辑器</span><span class="sxs-lookup"><span data-stu-id="ff18a-197">Editor opens at Restricted level</span></span>  <br/> |
|<span data-ttu-id="ff18a-198">**受限**</span><span class="sxs-lookup"><span data-stu-id="ff18a-198">**Restricted**</span></span> <br/> |<span data-ttu-id="ff18a-199">无法打开</span><span class="sxs-lookup"><span data-stu-id="ff18a-199">Fails to open</span></span>  <br/> |<span data-ttu-id="ff18a-200">无法打开</span><span class="sxs-lookup"><span data-stu-id="ff18a-200">Fails to open</span></span>  <br/> |<span data-ttu-id="ff18a-201">在"受限"级别打开编辑器</span><span class="sxs-lookup"><span data-stu-id="ff18a-201">Editor opens at Restricted level</span></span>  <br/> |
   
## <a name="specifying-a-security-level"></a><span data-ttu-id="ff18a-202">指定安全级别</span><span class="sxs-lookup"><span data-stu-id="ff18a-202">Specifying a security level</span></span>

<span data-ttu-id="ff18a-p109">InfoPath 表单设计器将根据您要在表单中使用的功能来自动选择相应的安全级别（"受限"或"域"）。安全设置始终要尽可能地具有限制性（从"受限"开始），以帮助确保您和您的数据得到较高级别的保护。通过执行以下这些步骤，用户可以手动覆盖这一自动设置以选择更适合表单的安全级别：</span><span class="sxs-lookup"><span data-stu-id="ff18a-p109">The InfoPath form designer automatically selects the appropriate security level (either Restricted or Domain) based on the features that you are using in the form. The security setting is always as restrictive as possible, starting at Restricted, to help ensure a greater level of protection for you and your data. Users can manually override this automated setting to select a level of security that is more appropriate for the form by following these steps:</span></span>
  
1. <span data-ttu-id="ff18a-206">Click the **File** tab, and then click **Form Options** on the **Info** tab.</span><span class="sxs-lookup"><span data-stu-id="ff18a-206">Click the **File** tab, and then click **Form Options** on the **Info** tab.</span></span> 
    
2. <span data-ttu-id="ff18a-207">In the **Categories** list, click **Security and Trust**.</span><span class="sxs-lookup"><span data-stu-id="ff18a-207">In the **Categories** list, click **Security and Trust**.</span></span>
    
3. <span data-ttu-id="ff18a-208">Uncheck the **Automatically determine security level (recommended)** check box.</span><span class="sxs-lookup"><span data-stu-id="ff18a-208">Uncheck the **Automatically determine security level (recommended)** check box.</span></span> 
    
4. <span data-ttu-id="ff18a-209">选择需要的安全级别。</span><span class="sxs-lookup"><span data-stu-id="ff18a-209">Select the desired security level.</span></span>
    
## <a name="mail-deployment-and-browser-enabled-form-templates"></a><span data-ttu-id="ff18a-210">邮件部署和启用浏览器功能的表单模板</span><span class="sxs-lookup"><span data-stu-id="ff18a-210">Mail deployment and browser-enabled form templates</span></span>

<span data-ttu-id="ff18a-211">InfoPath 允许你将表单模板作为电子邮件附件发送, 并将其从一个位置移动到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="ff18a-211">InfoPath allows you to send your form templates as an attachment to an email message and to move them from one location to another.</span></span> <span data-ttu-id="ff18a-212">邮件部署是一种便捷而有效的方式，它可以在办公室之间分发表单以供使用，也可以将表单部署到远程用户。</span><span class="sxs-lookup"><span data-stu-id="ff18a-212">Mail deployment is an easy and effective way to distribute forms for interoffice use and also to deploy forms to remote users.</span></span>
  
<span data-ttu-id="ff18a-213">此外，如果您具有包含 InfoPath Forms Services 的 Microsoft SharePoint Server 2010，则可以创建表单模板以便未安装 InfoPath 的用户可以在 Web 浏览器中填写表单。</span><span class="sxs-lookup"><span data-stu-id="ff18a-213">Alternatively, if you have Microsoft SharePoint Server 2010 with InfoPath Forms Services available, you can create form templates that enable users who do not have InfoPath installed to fill out forms in a Web browser.</span></span>
  
## <a name="understanding-form-identity"></a><span data-ttu-id="ff18a-214">了解表单标识</span><span class="sxs-lookup"><span data-stu-id="ff18a-214">Understanding form identity</span></span>

<span data-ttu-id="ff18a-p111">InfoPath Designer 中的所有表单都是通过标识来创建的。此标识信息可帮助 InfoPath 将表单与缓存中的表单模板相关联，而且在将表单张贴到共享位置时，还可帮助检索对表单的更新。默认情况下，InfoPath 可为表单模板创建两种标识：表单 ID 和访问路径。</span><span class="sxs-lookup"><span data-stu-id="ff18a-p111">All forms in the InfoPath designer are created with an identity. This identity information helps InfoPath associate forms with form templates in the cache and to retrieve updates to forms when they are posted to a shared location. By default, InfoPath creates two identities for form templates: a Form ID and an Access Path.</span></span> 
  
### <a name="form-id"></a><span data-ttu-id="ff18a-218">表单 ID</span><span class="sxs-lookup"><span data-stu-id="ff18a-218">Form ID</span></span>

<span data-ttu-id="ff18a-p112">表单 ID 是基于前缀、表单名称和表单命名空间的唯一标识符。标识符应该是可用于将表单文件与客户端计算机缓存中的相关表单模板正确关联的唯一名称。表单 ID 指定为表单定义文件 (.xsf) 中的名称属性（例如  `name="urn:MyForm:MyCompany:Template1:myXSD-1583-78-G3V94-23-47"`）。</span><span class="sxs-lookup"><span data-stu-id="ff18a-p112">The Form ID is a unique identifier based on a prefix, the form name, and the form namespace. The identifier should be a unique name that can be used to correctly associate form files with the associated form template in the client computer cache. The Form ID is specified as the name attribute (for example,  `name="urn:MyForm:MyCompany:Template1:myXSD-1583-78-G3V94-23-47"`) in the form definition file (.xsf).</span></span> 
  
### <a name="access-path"></a><span data-ttu-id="ff18a-222">访问路径</span><span class="sxs-lookup"><span data-stu-id="ff18a-222">Access Path</span></span>

<span data-ttu-id="ff18a-p113">访问路径是一种位置标识符，用于确定表单模板的正确位置和接收更新的位置。保存或发布表单模板时，保存或发布位置将成为默认访问路径。每次在客户端计算机上打开表单时，该表单都会尝试将自身与缓存表单相关联。它将尝试按照下列顺序进行关联：</span><span class="sxs-lookup"><span data-stu-id="ff18a-p113">The Access Path is a location identifier that is used to determine the correct location for the form template and also the location to receive updates. When saved or published, where the form template is saved or published becomes the default Access Path. Each time that a form is opened on the client computer, the form attempts to associate itself with a cached form. It will attempt to do this in the following order:</span></span>
  
1. <span data-ttu-id="ff18a-227">通过匹配的表单 ID 查找完全信任的表单模板。</span><span class="sxs-lookup"><span data-stu-id="ff18a-227">Look for a fully trusted form template with a matching Form ID.</span></span>
    
2. <span data-ttu-id="ff18a-228">通过匹配的访问路径来查找缓存中的表单模板。</span><span class="sxs-lookup"><span data-stu-id="ff18a-228">Look for a form template in the cache with a matching Access Path.</span></span>
    
3. <span data-ttu-id="ff18a-229">通过匹配的表单 ID 来查找缓存中的表单模板。</span><span class="sxs-lookup"><span data-stu-id="ff18a-229">Look for a form template in the cache with a matching Form ID.</span></span>
    
<span data-ttu-id="ff18a-p114">完成匹配后，将通过相关的表单模板来打开表单。如果是通过访问路径进行的匹配，InfoPath 将使用访问路径来检索对表单模板的更新。此方法简化了企业管理、维护及表单更新过程。如果无法进行匹配且信任级别为"域"，该表单将不会打开。访问路径指定为表单定义文件 (.xsf) 中的 **publishUrl** 属性。</span><span class="sxs-lookup"><span data-stu-id="ff18a-p114">Once matched, the form will open with the associated form template. In cases in which the match was made with an Access Path, InfoPath will use the Access Path to retrieve updates to the form template. This method simplifies enterprise administration, maintenance, and update of forms. In cases in which the match cannot be made and the trust level is Domain, the form will not open. The Access Path is specified as the **publishUrl** attribute in the form definition file (.xsf).</span></span> 
  
<span data-ttu-id="ff18a-235">正如每个表单模板都有两个标识属性一样，还存在一组启发方式，它们根据表单模板的条件（是具有访问路径、表单 ID，还是两者都具有）和网络连接的状态来专门确定缓存中的结果条目。</span><span class="sxs-lookup"><span data-stu-id="ff18a-235">Just as there are two identification properties for each form template, there is a set of heuristics to specifically determine the resulting entries in the cache, based on the condition of the form template (whether it has an Access Path, a Form ID, or both) and the state of the network connection.</span></span>
  
## <a name="designing-a-form-to-send-as-an-attachment-to-an-email-message"></a><span data-ttu-id="ff18a-236">将表单设计为以电子邮件附件形式发送</span><span class="sxs-lookup"><span data-stu-id="ff18a-236">Designing a form to send as an attachment to an email message</span></span>

<span data-ttu-id="ff18a-237">在 InfoPath 设计器中创建的所有表单都可以作为电子邮件的附件发送给用户。</span><span class="sxs-lookup"><span data-stu-id="ff18a-237">All forms that are created in the InfoPath designer can be sent to users as an attachment to an email message.</span></span> <span data-ttu-id="ff18a-238">电子邮件部署是一种用于分发表单以供内部使用的简单且有效的方法, 也可以将表单部署到远程用户。</span><span class="sxs-lookup"><span data-stu-id="ff18a-238">Email deployment is an easy and effective way to distribute forms for interoffice use and also to deploy forms to remote users.</span></span>
  
### <a name="to-mail-a-form-template-to-other-users"></a><span data-ttu-id="ff18a-239">通过邮件向其他用户发送表单模板</span><span class="sxs-lookup"><span data-stu-id="ff18a-239">To mail a form template to other users</span></span>

1. <span data-ttu-id="ff18a-240">单击 "**文件**" 选项卡, 单击 "**发布**", 然后单击 "**电子邮件**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="ff18a-240">Click the **File** tab, click **Publish**, and then click the **Email** button.</span></span> 
    
2. <span data-ttu-id="ff18a-241">Fill out the next two pages of the **Publishing Wizard** clicking **Next** to continue after each page, and then click **Publish**.</span><span class="sxs-lookup"><span data-stu-id="ff18a-241">Fill out the next two pages of the **Publishing Wizard** clicking **Next** to continue after each page, and then click **Publish**.</span></span>
    
3. <span data-ttu-id="ff18a-242">将显示一封电子邮件, 使您能够填写收件人列表以及您可能会遇到的任何其他说明。</span><span class="sxs-lookup"><span data-stu-id="ff18a-242">An email message is displayed enabling you to fill in the list of recipients and any additional instructions that you may have for them.</span></span>
    
4. <span data-ttu-id="ff18a-243">After you are finished, click **Send**.</span><span class="sxs-lookup"><span data-stu-id="ff18a-243">After you are finished, click **Send**.</span></span> <span data-ttu-id="ff18a-244">The form and the form template will be attached to the message.</span><span class="sxs-lookup"><span data-stu-id="ff18a-244">The form and the form template will be attached to the message.</span></span>
    
## <a name="email-deployment-restricted-domain-and-full-trust-form-templates"></a><span data-ttu-id="ff18a-245">电子邮件部署: 受限制的域和完全信任的表单模板</span><span class="sxs-lookup"><span data-stu-id="ff18a-245">Email deployment: restricted, domain, and Full Trust form templates</span></span>

<span data-ttu-id="ff18a-246">通过电子邮件部署受限制的表单模板允许从任何位置打开无数据连接的动态表单。</span><span class="sxs-lookup"><span data-stu-id="ff18a-246">Email deployment of Restricted form templates allows dynamic forms without data connections to be opened from anywhere.</span></span> <span data-ttu-id="ff18a-247">收件人可以直接从 Microsoft Outlook 2010 或从收件人保存附件的任何位置打开作为电子邮件附件发送的表单模板。</span><span class="sxs-lookup"><span data-stu-id="ff18a-247">Recipients can open form templates sent as email attachments either directly from Microsoft Outlook 2010 or from wherever the recipient has saved the attachment.</span></span> <span data-ttu-id="ff18a-248">此外，Outlook 2010 还允许用户直接在邮件中编辑表单。</span><span class="sxs-lookup"><span data-stu-id="ff18a-248">Additionally, Outlook 2010 allows users to edit forms directly in the message.</span></span>
  
<span data-ttu-id="ff18a-249">必须从其发布位置打开具有域信任级别的表单模板, 但通过发布到 "发布向导" 中的电子邮件收件人列表, 可以将其作为电子邮件的附件发送。</span><span class="sxs-lookup"><span data-stu-id="ff18a-249">Form templates with the Domain trust level must be opened from their published location, but by publishing to a list of email recipients in the Publishing Wizard, they can be sent as an attachment to an email message.</span></span> <span data-ttu-id="ff18a-250">When the attachment is opened, it functions as a link to the actual published location of the template.</span><span class="sxs-lookup"><span data-stu-id="ff18a-250">When the attachment is opened, it functions as a link to the actual published location of the template.</span></span> <span data-ttu-id="ff18a-251">The form template at that location is what is actually opened in the InfoPath editor.</span><span class="sxs-lookup"><span data-stu-id="ff18a-251">The form template at that location is what is actually opened in the InfoPath editor.</span></span>
  
<span data-ttu-id="ff18a-252">使用以电子邮件附件形式发送的域级表单模板类似于使用任何其他类型的文档;例如, microsoft Excel 工作簿或 microsoft Word 文档。</span><span class="sxs-lookup"><span data-stu-id="ff18a-252">Using a Domain-level form template sent as an email attachment resembles using any other kind of document; for example, a Microsoft Excel workbook or a Microsoft Word document.</span></span> <span data-ttu-id="ff18a-253">用户只需单击表单即可打开并使用它。</span><span class="sxs-lookup"><span data-stu-id="ff18a-253">A user can just click on the form to open and use it.</span></span> <span data-ttu-id="ff18a-254">此外，用户还可以获得"域"级别更新的所有好处。</span><span class="sxs-lookup"><span data-stu-id="ff18a-254">In addition, all the benefits of Domain-level updates are available to users.</span></span>
  
<span data-ttu-id="ff18a-255">您可以通过电子邮件发送请求完全信任访问权限的表单模板, 但必须对这些模板进行签名, 否则将不允许打开这些模板。</span><span class="sxs-lookup"><span data-stu-id="ff18a-255">You can email form templates that request Full Trust access, but these templates must be signed or they will not be allowed to open.</span></span> <span data-ttu-id="ff18a-256">请求域或受限访问权限的表单模板无需签名即可作为电子邮件附件发送。</span><span class="sxs-lookup"><span data-stu-id="ff18a-256">Form templates requesting Domain or Restricted access do not have to be signed to be sent as an email attachment.</span></span> <span data-ttu-id="ff18a-257">除非要查看能否自动更新模板，否则 InfoPath 不会检查或验证签名，即使对模板进行了签名也是如此。</span><span class="sxs-lookup"><span data-stu-id="ff18a-257">InfoPath does not check or verify the signature, even if the template is signed, except to see whether it can be updated automatically.</span></span> <span data-ttu-id="ff18a-258">您可以对"域"或"受限"表单模板进行数字签名，并且仍能够进行自动更新。</span><span class="sxs-lookup"><span data-stu-id="ff18a-258">You could digitally sign a Domain or Restricted form template and still have automatic update capability.</span></span> <span data-ttu-id="ff18a-259">在这种情况下，数字签名将阻止显示任何缓存冲突消息。</span><span class="sxs-lookup"><span data-stu-id="ff18a-259">In this case, the digital signature will prevent any cache conflict messages from appearing.</span></span>
  
## <a name="sharing-forms-by-email-message-or-from-a-common-shared-location"></a><span data-ttu-id="ff18a-260">通过电子邮件或从公用共享位置共享表单</span><span class="sxs-lookup"><span data-stu-id="ff18a-260">Sharing forms by email message or from a common shared location</span></span>

<span data-ttu-id="ff18a-261">创建将通过电子邮件部署的表单时, 应考虑一些问题。</span><span class="sxs-lookup"><span data-stu-id="ff18a-261">Certain questions should be considered when you are creating a form that will be deployed by email message.</span></span>
  
- <span data-ttu-id="ff18a-p121">**是否要定期更新表单？** 如果要开发必须定期更新的表单，则应在将表单发送给其他用户之前，将其发布到共享位置。这将允许您通过将更新的版本发布到共享位置来更新表单，还允许您即时将表单模板分发给那些对共享位置可能没有访问权限的用户。</span><span class="sxs-lookup"><span data-stu-id="ff18a-p121">**Will your form be updated regularly?** If you are developing a form that must be updated regularly, the form should be published to a shared location before it is sent to other users. This practice enables you to update the form by publishing newer versions to the shared location but it also enables you to immediately distribute the form template to users who may not have access to the shared location.</span></span> 
    
   <span data-ttu-id="ff18a-265">如果表单已更新, 然后通过电子邮件进行分发, 则当用户尝试打开新表单时, 将会收到缓存冲突消息, 如果用户在其计算机上存储了旧版本, 并且访问路径已更改。</span><span class="sxs-lookup"><span data-stu-id="ff18a-265">If a form is updated and then distributed by email message, users will get a cache conflict message when they try to open the new form, if they have an older version stored on their computer and the Access Path has changed.</span></span> <span data-ttu-id="ff18a-266">系统将提示用户选择要使用的版本。</span><span class="sxs-lookup"><span data-stu-id="ff18a-266">The user will be prompted to choose which version they want to use.</span></span> <span data-ttu-id="ff18a-267">即使已更新的表单与用户计算机上的表单相同，用户仍然会收到缓存冲突消息，同时系统会提示用户选择要使用哪一份表单。</span><span class="sxs-lookup"><span data-stu-id="ff18a-267">Even if the updated form is the same as the one on the user's computer, the user will get a cache conflict message and be prompted to choose which copy they want to use.</span></span> <span data-ttu-id="ff18a-268">后面一种情况下的最佳实践是改为从共享位置来共享表单。</span><span class="sxs-lookup"><span data-stu-id="ff18a-268">The best practice to use in the latter case is to share the form from a shared location instead.</span></span>
    
- <span data-ttu-id="ff18a-269">**您的表单是否访问数据连接或使用"受限"安全级别所不支持的其他功能？**</span><span class="sxs-lookup"><span data-stu-id="ff18a-269">**Does your form access a data connection or use other features not supported at the Restricted security level?**</span></span> <span data-ttu-id="ff18a-270">如果开发请求"域"安全级别的表单，InfoPath 会要求您将该表单发布到共享位置以便用户能够打开它。</span><span class="sxs-lookup"><span data-stu-id="ff18a-270">If you are developing a form that requires Domain-level security, InfoPath requires you to publish the form to a shared location for users to be able to open it.</span></span> <span data-ttu-id="ff18a-271">由于表单模板将仅在所请求的安全级别打开, 如果 InfoPath 无法授予域级安全, 则直接从电子邮件打开的表单将无法打开。</span><span class="sxs-lookup"><span data-stu-id="ff18a-271">Because form templates will only open at the security level they request, forms opened directly from an email message will not open if InfoPath cannot grant Domain-level security.</span></span> 
    
## <a name="benefits-of-using-signed-form-templates"></a><span data-ttu-id="ff18a-272">使用已签名表单模板的好处</span><span class="sxs-lookup"><span data-stu-id="ff18a-272">Benefits of using signed form templates</span></span>

- <span data-ttu-id="ff18a-273">允许使用"完全信任"安全级别打开表单模板。</span><span class="sxs-lookup"><span data-stu-id="ff18a-273">It allows the form template to open with Full Trust security.</span></span>
    
- <span data-ttu-id="ff18a-274">如果将表单移至新位置，还可避免出现缓存冲突消息。</span><span class="sxs-lookup"><span data-stu-id="ff18a-274">It avoids the cache conflict message if the form is moved to a new location.</span></span>
    
<span data-ttu-id="ff18a-p124">此外，如果对表单模板进行了签名，则还可以受益于自动更新功能。有关详细信息，请参阅[部署已签署的 InfoPath 表单模板](deploying-signed-infopath-form-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="ff18a-p124">Additionally, if a form template is signed, you get the added benefit of the automatic update functionality. For more information, see [Deploying Signed InfoPath Form Templates](deploying-signed-infopath-form-templates.md).</span></span>
  
### <a name="example-updating-domain-or-restricted-templates"></a><span data-ttu-id="ff18a-277">示例: 更新域或受限制的模板</span><span class="sxs-lookup"><span data-stu-id="ff18a-277">Example: Updating domain or restricted templates</span></span>

<span data-ttu-id="ff18a-278">下面的示例展示了请求域或受限访问权限的更新的签名表单模板如何覆盖较旧的副本:</span><span class="sxs-lookup"><span data-stu-id="ff18a-278">The following example shows how an updated, signed form template requesting either Domain or Restricted access can overwrite an older copy:</span></span> 
  
1. <span data-ttu-id="ff18a-279">"A"将签名的表单模板发送到"B"。</span><span class="sxs-lookup"><span data-stu-id="ff18a-279">"A" sends a signed form template to "B".</span></span>
    
2. <span data-ttu-id="ff18a-280">"B"打开该表单模板。</span><span class="sxs-lookup"><span data-stu-id="ff18a-280">"B" opens the form template.</span></span>
    
3. <span data-ttu-id="ff18a-281">"A"更新该表单模板（例如，添加更多域）。</span><span class="sxs-lookup"><span data-stu-id="ff18a-281">"A" updates the form template (for example, adds more fields).</span></span>
    
4. <span data-ttu-id="ff18a-282">"A"将更新的表单模板发送到"B"。</span><span class="sxs-lookup"><span data-stu-id="ff18a-282">"A" sends the updated form template to "B".</span></span>
    
5. <span data-ttu-id="ff18a-283">"B"打开更新的表单模板。</span><span class="sxs-lookup"><span data-stu-id="ff18a-283">"B" opens the updated form template.</span></span>
    
### <a name="example-deploying-restricted-form-templates-on-an-extranet"></a><span data-ttu-id="ff18a-284">示例: 在 extranet 上部署受限制的表单模板</span><span class="sxs-lookup"><span data-stu-id="ff18a-284">Example: Deploying restricted form templates on an extranet</span></span>
  
1. <span data-ttu-id="ff18a-285">将 "域" 表单模板保存在运行 Microsoft SharePoint Foundation 2010 的网站上。</span><span class="sxs-lookup"><span data-stu-id="ff18a-285">Save the Domain form template on a website that is running Microsoft SharePoint Foundation 2010.</span></span>
    
2. <span data-ttu-id="ff18a-286">将该表单模板的安全级别更改为"受限"。</span><span class="sxs-lookup"><span data-stu-id="ff18a-286">Change the form template security level to Restricted.</span></span>
    
3. <span data-ttu-id="ff18a-287">将该表单模板保存到您的计算机桌面上。</span><span class="sxs-lookup"><span data-stu-id="ff18a-287">Save the form template on your computer desktop.</span></span>
    
4. <span data-ttu-id="ff18a-288">删除 URL（仅在用户能够访问原始发布位置时才需要这样做）。</span><span class="sxs-lookup"><span data-stu-id="ff18a-288">Remove the URL (required only if users have access to the original publish location).</span></span>
    
5. <span data-ttu-id="ff18a-289">向 Extranet 用户发送该表单。</span><span class="sxs-lookup"><span data-stu-id="ff18a-289">Send the form to users on an extranet.</span></span>
    
6. <span data-ttu-id="ff18a-290">要求用户安装该表单。</span><span class="sxs-lookup"><span data-stu-id="ff18a-290">Have the users install the form.</span></span>
    
7. <span data-ttu-id="ff18a-291">要求用户在填写表单后将其返回给您。</span><span class="sxs-lookup"><span data-stu-id="ff18a-291">Have users send the form back to you after filling it out.</span></span>
    
8. <span data-ttu-id="ff18a-292">将表单保存回运行 SharePoint Foundation 2010 的网站, 并使用 "**表单库设置**" 页中的 "将**文档重新链接到此库**" 选项重新链接表单。</span><span class="sxs-lookup"><span data-stu-id="ff18a-292">Save the form back to the website that is running SharePoint Foundation 2010 and relink the form by using the **Relink documents to this Library** option in the **Form Library Settings** page.</span></span> 
    
## <a name="signature-verification-failure"></a><span data-ttu-id="ff18a-293">签名验证失败</span><span class="sxs-lookup"><span data-stu-id="ff18a-293">Signature verification failure</span></span>

<span data-ttu-id="ff18a-p125">请求"完全信任"访问权限，但无法验证其签名的已签名表单模板将无法打开。签名验证会由于以下原因而失败：</span><span class="sxs-lookup"><span data-stu-id="ff18a-p125">A signed form template that requests full trust access but for which the signature cannot be authenticated will not open. Signature verification can fail for any of the following reasons:</span></span>
  
- <span data-ttu-id="ff18a-296">根证书不在受信任的根证书存储区内。</span><span class="sxs-lookup"><span data-stu-id="ff18a-296">The root certificate is not in the trusted root certificate store.</span></span>
    
- <span data-ttu-id="ff18a-297">用于对表单模板进行签名的证书已过期。</span><span class="sxs-lookup"><span data-stu-id="ff18a-297">The certificate that was used to sign the form template has expired.</span></span>
    
- <span data-ttu-id="ff18a-298">用于对表单模板进行签名的证书已被吊销。</span><span class="sxs-lookup"><span data-stu-id="ff18a-298">The certificate that was used to sign the form template was revoked.</span></span>
    
- <span data-ttu-id="ff18a-299">表单模板上的签名已损坏（有可能是在签名表单模板后更改了该模板）。</span><span class="sxs-lookup"><span data-stu-id="ff18a-299">The signature on the form template is corrupted (an indication that the form template was altered after it was signed).</span></span>
    
<span data-ttu-id="ff18a-300">如果已签名的表单模板请求"域"或"受限"访问权限，那么除非是要确定该模板能否自动更新，否则 InfoPath 将不会检查或验证签名。</span><span class="sxs-lookup"><span data-stu-id="ff18a-300">If a signed form template requests Domain or Restricted access, InfoPath will not check or verify the signature except to determine whether the template can be updated automatically.</span></span>
  
## <a name="infrastructure-registry-keys-for-form-migration-open-behavior"></a><span data-ttu-id="ff18a-301">表单迁移打开行为的基础结构注册表项</span><span class="sxs-lookup"><span data-stu-id="ff18a-301">Infrastructure registry keys for form migration open behavior</span></span>

<span data-ttu-id="ff18a-p126">如果用户尝试打开某表单，而该表单是按其表单 ID 与表单模板进行匹配的，那么当表单模板具有"域"信任级别，而该域与表单的  *href*  属性不匹配时，InfoPath 将显示一则错误消息。这将阻止打开未使用表单模板明确创建的表单。</span><span class="sxs-lookup"><span data-stu-id="ff18a-p126">When a user attempts to open a form, and the form is matched against a form template by its Form ID, InfoPath will display an error message if the form template has a Domain trust level and the domain does not match the  *href*  attribute of the form. This prevents forms from being opened that were not explicitly created by using the form template.</span></span> 
  
<span data-ttu-id="ff18a-p127">InfoPath 不允许具有同一表单 ID 的表单模板共存。系统管理员可借助另外四个注册表项来让用户选择是否允许依据表单模板打开 XML 文件。该模型还允许管理员设置所需的表单打开行为。</span><span class="sxs-lookup"><span data-stu-id="ff18a-p127">InfoPath does not allow form templates with the same Form ID to coexist. Four additional registry keys help system administrators give users the option of whether to allow the XML file to open against a form template. This model also lets administrators set the open behavior they want for forms.</span></span>
  
<span data-ttu-id="ff18a-p128">下表描述了这些注册表项的默认设置。如果缺少这些注册表项，则会强制使用该表中指定的默认值。</span><span class="sxs-lookup"><span data-stu-id="ff18a-p128">The following table describes the default settings for the registry keys. If these registry keys are absent, the default value specified in the table will be enforced.</span></span>
  
<span data-ttu-id="ff18a-p129">"名称"值对应于 Internet Explorer 域设置。这些值确定这些安全区域中的表单打开行为，即，阻止或允许打开表单，或者让用户选择是否打开表单。</span><span class="sxs-lookup"><span data-stu-id="ff18a-p129">The Name values correspond to the Internet Explorer domain settings. These values determine the form open behavior in these security zones, either blocking or allowing the opening of the form, or giving the user the option to open the form.</span></span>
  
|<span data-ttu-id="ff18a-311">**"名称"值**</span><span class="sxs-lookup"><span data-stu-id="ff18a-311">**Name value**</span></span>|<span data-ttu-id="ff18a-312">**阻止**</span><span class="sxs-lookup"><span data-stu-id="ff18a-312">**Block**</span></span>|<span data-ttu-id="ff18a-313">**用户界面**</span><span class="sxs-lookup"><span data-stu-id="ff18a-313">**User Interface**</span></span>|<span data-ttu-id="ff18a-314">**允许**</span><span class="sxs-lookup"><span data-stu-id="ff18a-314">**Allow**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ff18a-315">**Internet**</span><span class="sxs-lookup"><span data-stu-id="ff18a-315">**Internet**</span></span> <br/> |<span data-ttu-id="ff18a-316">X</span><span class="sxs-lookup"><span data-stu-id="ff18a-316">X</span></span>  <br/> |||
|<span data-ttu-id="ff18a-317">**Intranet**</span><span class="sxs-lookup"><span data-stu-id="ff18a-317">**Intranet**</span></span> <br/> ||<span data-ttu-id="ff18a-318">X</span><span class="sxs-lookup"><span data-stu-id="ff18a-318">X</span></span>  <br/> ||
|<span data-ttu-id="ff18a-319">**客户端计算机**</span><span class="sxs-lookup"><span data-stu-id="ff18a-319">**Client Computer**</span></span> <br/> |||<span data-ttu-id="ff18a-320">X</span><span class="sxs-lookup"><span data-stu-id="ff18a-320">X</span></span>  <br/> |
|<span data-ttu-id="ff18a-321">**受信任的站点**</span><span class="sxs-lookup"><span data-stu-id="ff18a-321">**Trusted Site**</span></span> <br/> |||<span data-ttu-id="ff18a-322">X</span><span class="sxs-lookup"><span data-stu-id="ff18a-322">X</span></span>  <br/> |
   
<span data-ttu-id="ff18a-323">注册表项路径为`HKEY_CURRENT_USER\Software\Microsoft\Office\14.0\InfoPath\Open Behaviors`。</span><span class="sxs-lookup"><span data-stu-id="ff18a-323">The registry key path is `HKEY_CURRENT_USER\Software\Microsoft\Office\14.0\InfoPath\Open Behaviors`.</span></span>

<span data-ttu-id="ff18a-324">表单打开行为按如下所示定义：</span><span class="sxs-lookup"><span data-stu-id="ff18a-324">The form open behavior is defined as follows:</span></span>
  
- <span data-ttu-id="ff18a-p130">`Block [REG_DWORD = 0]`- 将显示一个包含"帮助"按钮的错误对话框。当表单运行在指定安全区域且与模板所在域不匹配时，InfoPath 将不允许打开 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="ff18a-p130">`Block [REG_DWORD = 0]`- An error dialog with a Help button will be shown. InfoPath will not allow the XML file to open when the form is running in the specified security zone and does not match the template domain.</span></span> 
    
- <span data-ttu-id="ff18a-p131">`User Interface [REG_DWORD = 1]`- 将显示"是/否"对话框。当表单运行在指定安全区域且与模板所在域不匹配时，InfoPath 将提示用户依据表单模板打开 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="ff18a-p131">`User Interface [REG_DWORD = 1]`- The Yes/No dialog box will be shown. InfoPath will prompt the user to open the XML file against the form template when the form is running in the specified security zone and does not match the template domain.</span></span> 
    
- <span data-ttu-id="ff18a-p132">`Allow [REG_DWORD = 2]`- XML 文件将打开，并且不显示错误或警告对话框。当表单运行在指定安全区域且与模板所在域不匹配时，InfoPath 将允许打开 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="ff18a-p132">`Allow [REG_DWORD = 2]`- The XML file will open without an error or warning dialog. InfoPath will allow the XML file to open when the form is running in the specified security zone and does not match the template domain.</span></span> 
    
<span data-ttu-id="ff18a-p133">如果依据在"域"安全级别运行的表单模板打开表单，并且该模板的"缓存位置"（即，表单的缓存位置）所在的安全域与表单的 **href** 属性不匹配，InfoPath 将检查注册表以定义表单打开行为。允许的行为基于模板所在的安全区域（  *CachedFromLocation*  值）。</span><span class="sxs-lookup"><span data-stu-id="ff18a-p133">If a form is opened against a form template running at the Domain security level, and the security domain of the template's "cached from" location (that is, where the form is cached from) and the form's **href** attribute do not match, InfoPath will check the registry to define the form open behavior. Allowed behavior will be based on the security zone in which the template is located (the  *CachedFromLocation*  value).</span></span> 
  
<span data-ttu-id="ff18a-333">例如，如果根据表单 ID 而不是访问路径，将表单与表单模板进行匹配，并且从 Internet 位置缓存了该表单模板，InfoPath 将显示一则包含"帮助"按钮的错误对话框。</span><span class="sxs-lookup"><span data-stu-id="ff18a-333">For example, when a form matches a form template based on Form ID but not on Access Path, and the form template is cached from an Internet location, InfoPath will show an error dialog with a Help button.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ff18a-334">[!注释] 如果域是 Internet Explorer"受限"域，InfoPath 表单将不会打开；因此，没有 Internet Explorer"受限"站点的相关注册表项。</span><span class="sxs-lookup"><span data-stu-id="ff18a-334">InfoPath forms will not open when the domain is an Internet Explorer Restricted domain; therefore, there is no registry key for Internet Explorer Restricted Sites.</span></span> 
  

