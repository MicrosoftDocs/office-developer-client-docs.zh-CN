---
title: 部署已签署的 InfoPath 表单模板
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 8345a4bc-ad7b-d0b0-7615-f77ade35006d
description: 在阅读本主题之前，请先查看 更多 InfoPath 表单安全性概念中的经过签名的表单模板一节，以了解已签名表单模板的安全性。还需查看安全级别、电子邮件部署和远程表单模板主题中的相关信息和讨论内容。
ms.openlocfilehash: 76cc6dfdbd2c01827182c348281a98ad7cd17b69
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426798"
---
# <a name="deploying-signed-infopath-form-templates"></a><span data-ttu-id="58471-104">部署已签署的 InfoPath 表单模板</span><span class="sxs-lookup"><span data-stu-id="58471-104">Deploying Signed InfoPath Form Templates</span></span>

<span data-ttu-id="58471-p102">在阅读本主题之前，请先查看 [更多 InfoPath 表单安全性概念](additional-infopath-form-security-concepts.md)中的"经过签名的表单模板"一节，以了解已签名表单模板的安全性。还需查看[安全级别、电子邮件部署和远程表单模板](security-levels-email-deployment-and-remote-form-templates.md)主题中的相关信息和讨论内容。</span><span class="sxs-lookup"><span data-stu-id="58471-p102">Before reading this topic, see the "Signed Form Templates" section in [Additional InfoPath Form Security Concepts](additional-infopath-form-security-concepts.md) for an understanding of signed form template security. Information and discussions in the [Security Levels, E-Mail Deployment, and Remote Form Templates](security-levels-email-deployment-and-remote-form-templates.md) topic are also relevant.</span></span> 
  
## <a name="digitally-signing-a-form-template"></a><span data-ttu-id="58471-107">对表单模板进行数字签名</span><span class="sxs-lookup"><span data-stu-id="58471-107">Digitally Signing a Form Template</span></span>

<span data-ttu-id="58471-108">如果对表单模板进行数字签名，可将表单模板的安全级别设置为“完全信任”，这意味着表单可以在用户计算机或其他域上访问文件和设置。</span><span class="sxs-lookup"><span data-stu-id="58471-108">If you digitally sign a form template, you can set the security level for the form template to Full Trust, which means the form can access files and settings on the user's computer or on a different domain.</span></span> <span data-ttu-id="58471-109">（此外，如果你愿意，对表单模板进行数字签名不会阻止你使用其他安全级别。</span><span class="sxs-lookup"><span data-stu-id="58471-109">(Also, digitally signing a form template does not prevent you from using other security levels, if you prefer.</span></span> <span data-ttu-id="58471-110">将已签名模板的安全级别设置为域或受限制的安全级别。）还可以将已签名表单模板部署给使用电子邮件程序的用户，然后通过将更新后的版本作为电子邮件附件发送给用户来自动更新已签名表单模板，请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="58471-110">You set the security level of a signed form template to the Domain or Restricted security level.) In addition, you can deploy the signed form template to users who are using an email program and then later automatically update the signed form template by sending the updated version to the users as an attachment to an email message, follow these steps:</span></span>
  
### <a name="to-digitally-sign-a-form-template"></a><span data-ttu-id="58471-111">对表单模板进行数字签名</span><span class="sxs-lookup"><span data-stu-id="58471-111">To digitally sign a form template</span></span>

1. <span data-ttu-id="58471-112">在 InfoPath 设计器中，单击“文件”选项卡，然后单击“信息”选项卡上的“表单选项”。</span><span class="sxs-lookup"><span data-stu-id="58471-112">In the InfoPath designer, click the **File** tab, and then click **Form Options** on the **Info** tab.</span></span> 
    
2. <span data-ttu-id="58471-113">在“表单选项”对话框中单击“安全和信任”类别。</span><span class="sxs-lookup"><span data-stu-id="58471-113">In the **Form Options** dialog box, click the **Security and Trust** category.</span></span> 
    
3. <span data-ttu-id="58471-114">Under **Form Template Signature**, select the **Sign this form template** check box.</span><span class="sxs-lookup"><span data-stu-id="58471-114">Under **Form Template Signature**, select the **Sign this form template** check box.</span></span> 
    
4. <span data-ttu-id="58471-115">Click **Select Certificate**.</span><span class="sxs-lookup"><span data-stu-id="58471-115">Click **Select Certificate**.</span></span>
    
5. <span data-ttu-id="58471-116">In the **Select Certificate** dialog box, click the certificate that you want to use to digitally sign the form.</span><span class="sxs-lookup"><span data-stu-id="58471-116">In the **Select Certificate** dialog box, click the certificate that you want to use to digitally sign the form.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="58471-p104">The **Create Certificate** button in the **Form Options** dialog box can be used to generate a test certificate to sign a form template. The test certificate should be used to sign form templates for testing only. Test certificates should not be used to sign form templates that will be distributed publicly. Because the certificates are not issued by a Certificate Authority whose root certificate is already trusted on a user's computer, the test certificate will not validate correctly on the user's computer. If you deploy a form template signed with a test certificate, users of your form template will most likely be unable to open it.</span><span class="sxs-lookup"><span data-stu-id="58471-p104">The **Create Certificate** button in the **Form Options** dialog box can be used to generate a test certificate to sign a form template. The test certificate should be used to sign form templates for testing only. Test certificates should not be used to sign form templates that will be distributed publicly. Because the certificates are not issued by a Certificate Authority whose root certificate is already trusted on a user's computer, the test certificate will not validate correctly on the user's computer. If you deploy a form template signed with a test certificate, users of your form template will most likely be unable to open it.</span></span> 
  
## <a name="establishing-a-trusted-root-certificate-and-publisher"></a><span data-ttu-id="58471-122">创建受信任的根证书和发布者</span><span class="sxs-lookup"><span data-stu-id="58471-122">Establishing a Trusted Root Certificate and Publisher</span></span>

 <span data-ttu-id="58471-p105">用于对表单模板进行签名的证书的受信任根证书必须位于客户端计算机上的受信任根证书存储区内。否则，将无法验证表单模板的发布者，并且表单模板用户将无法使用用于信任发布者的选项。如果受信任根证书位于受信任的根证书存储区内，但受信任的发布者列表中不包含相应的发布者，则系统会提示用户并提供用于信任表单模板发布者的选项。</span><span class="sxs-lookup"><span data-stu-id="58471-p105">The trusted root certificate of the certificate that is used to sign the form template must be in the trusted root certificate store on the client computer. If not, the publisher of the form template cannot be verified, and users of your form template will not be given the option to trust the publisher. If the trusted root certificate is in the trusted root certificate store, but the publisher is not in the trusted publisher list, users are prompted and given the option to trust the publisher of the form template.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="58471-p106">如果已签名的表单模板请求"域"或"受限"访问权限，InfoPath 将使用该签名来验证在签署该表单模板后，它是否已被篡改。并且还会使用该签名确定能否自动更新该表单模板。</span><span class="sxs-lookup"><span data-stu-id="58471-p106">If a signed form template requests Domain or Restricted access, InfoPath will use the signature to verify that the form template was not tampered with after it was signed. InfoPath also uses the signature to determine whether the form template can be updated automatically.</span></span> 
  
## <a name="deploying-signed-form-templates-with-full-trust-access"></a><span data-ttu-id="58471-128">部署具有完全信任访问权限的已签名表单模板</span><span class="sxs-lookup"><span data-stu-id="58471-128">Deploying Signed Form Templates with Full Trust Access</span></span>

<span data-ttu-id="58471-p107">部署已签名的表单模板的主要方案是在完全信任的表单中启用自动更新等类似域的功能。请求完全信任访问权限的已签名表单模板与 *完全信任的表单*  具有相同的系统资源访问权限。有关完全信任的表单的工作方式以及如何创建和部署这些表单的详细讨论，请参阅 [了解完全信任的表单](understanding-fully-trusted-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="58471-p107">The primary scenario for deploying signed form templates is to enable domain-like functionality, such as automatic update, in full-trust forms. A signed form template requesting full-trust access has the same access to system resources as a  *fully trusted form*  . For a detailed discussion of how fully trusted forms work and how to create and deploy them, see [Understanding Fully Trusted Forms](understanding-fully-trusted-forms.md).</span></span>
  
<span data-ttu-id="58471-p108">但是，根据贵组织的计算环境，您可能更愿意使用已签名的表单模板或完全信任的表单。例如，不使用已注册的完全信任表单，而是使用请求"完全信任"访问权限的已签名表单模板会带来一些好处。请求"完全信任"访问权限的已签名表单模板具有以下优点：</span><span class="sxs-lookup"><span data-stu-id="58471-p108">However, depending on your organization's computing environment, you might prefer to use either signed form templates or fully trusted forms. For example, there are benefits to using a signed form template that requests full-trust access instead of a registered, fully trusted form. A signed form template requesting full-trust access has the following benefits:</span></span>
  
- <span data-ttu-id="58471-135">与未签名的完全信任的表单模板不同，无需对其进行注册。</span><span class="sxs-lookup"><span data-stu-id="58471-135">Does not have to be registered, unlike an unsigned, fully trusted form template.</span></span>
    
- <span data-ttu-id="58471-136">表单模板能够以静默方式自动更新。</span><span class="sxs-lookup"><span data-stu-id="58471-136">Enables silent automatic update of the form template.</span></span>
    
<span data-ttu-id="58471-p109">由于不必注册请求"完全信任"访问权限的已签名表单模板，因此无需使用安装程序包或脚本文件来部署该模板。该好处极大地简化了完全信任的表单模板的部署过程。</span><span class="sxs-lookup"><span data-stu-id="58471-p109">Because you do not have to register a signed form template that requests full-trust access, you do not have to use an installer package or script file to deploy it. This benefit greatly simplifies the deployment of a full-trust form template.</span></span>
  
<span data-ttu-id="58471-p110">在更新请求"完全信任"访问权限的已签名表单模板时，可以只向用户发送更新的模板或在共享位置更新该模板。当用户打开该更新模板时，不会出现提示，并且更新版本将以静默方式覆盖用户计算机上的较旧副本。</span><span class="sxs-lookup"><span data-stu-id="58471-p110">When you update your signed form template that requests full-trust access, you can just send the updated template to the user or update it in a shared location. When the user opens the updated template, the user will not be prompted, and the updated version will silently overwrite the older copy on the user's computer. If you updated the template in a shared location, the user will be able to use the updated copy without being prompted.</span></span>
  
<span data-ttu-id="58471-p111">如果要更新未签名的完全信任表单，则必须对该表单重新打包并重新注册它。此外，已安装的现有完全信任的表单模板只对本地计算机路径起作用，而对网络路径不起作用，这是因为注册过程不支持将本地计算机路径更改为网络路径。但是，因为需要证书才能对表单模板进行签名，所以，如果您不想购买证书，可以选择部署经过注册的完全信任的表单模板。</span><span class="sxs-lookup"><span data-stu-id="58471-p111">If you want to update an unsigned, fully trusted form, you must repackage your form and re-register it. Additionally, an existing, installed fully trusted form template works only for the path of the local computer but does not work for a network path, because the registration process does not support changing a local computer path to a network path. However, because a certificate is needed to sign a form template, you may prefer to deploy fully trusted, registered form templates, if you do not want to purchase a certificate.</span></span>
  
## <a name="deploying-signed-form-templates-with-domain-or-restricted-access"></a><span data-ttu-id="58471-145">部署具有"域"或"受限"访问权限的已签名的表单模板</span><span class="sxs-lookup"><span data-stu-id="58471-145">Deploying Signed Form Templates with Domain or Restricted Access</span></span>

<span data-ttu-id="58471-p112">具有"域"或"受限"安全级别的已签名表单模板还具有自动更新功能。例如，可以将已签名的表单模板发布到运行 Microsoft SharePoint Foundation 的服务器或具有"域"安全级别的服务器上的文档库。在共享位置更新该表单模板时，用户将自动获得更新的副本。</span><span class="sxs-lookup"><span data-stu-id="58471-p112">A signed form template that has a Domain or Restricted security level also has the advantage of the automatic update functionality. For example, you could publish a signed form template to a document library on a server that is running Microsoft SharePoint Foundation or on a server that has a Domain security level. When you update your form template in the shared location, users will get the updated copy automatically.</span></span>
  

