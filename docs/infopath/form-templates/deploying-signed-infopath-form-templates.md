---
title: 部署已签署的 InfoPath 表单模板
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 8345a4bc-ad7b-d0b0-7615-f77ade35006d
description: 在阅读本主题之前，请先查看 更多 InfoPath 表单安全性概念中的经过签名的表单模板一节，以了解已签名表单模板的安全性。还需查看安全级别、电子邮件部署和远程表单模板主题中的相关信息和讨论内容。
ms.openlocfilehash: 76cc6dfdbd2c01827182c348281a98ad7cd17b69
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303715"
---
# <a name="deploying-signed-infopath-form-templates"></a>部署已签署的 InfoPath 表单模板

在阅读本主题之前，请先查看 [更多 InfoPath 表单安全性概念](additional-infopath-form-security-concepts.md)中的"经过签名的表单模板"一节，以了解已签名表单模板的安全性。还需查看[安全级别、电子邮件部署和远程表单模板](security-levels-email-deployment-and-remote-form-templates.md)主题中的相关信息和讨论内容。 
  
## <a name="digitally-signing-a-form-template"></a>对表单模板进行数字签名

如果对表单模板进行数字签名，可将表单模板的安全级别设置为“完全信任”，这意味着表单可以在用户计算机或其他域上访问文件和设置。 （此外，如果你愿意，对表单模板进行数字签名不会阻止你使用其他安全级别。 将已签名模板的安全级别设置为域或受限制的安全级别。）还可以将已签名表单模板部署给使用电子邮件程序的用户，然后通过将更新后的版本作为电子邮件附件发送给用户来自动更新已签名表单模板，请按以下步骤操作：
  
### <a name="to-digitally-sign-a-form-template"></a>对表单模板进行数字签名

1. 在 InfoPath 设计器中，单击“文件”**** 选项卡，然后单击“信息”**** 选项卡上的“表单选项”****。 
    
2. 在“表单选项”**** 对话框中单击“安全和信任”**** 类别。 
    
3. Under **Form Template Signature**, select the **Sign this form template** check box. 
    
4. Click **Select Certificate**.
    
5. In the **Select Certificate** dialog box, click the certificate that you want to use to digitally sign the form. 
    
> [!NOTE]
> The **Create Certificate** button in the **Form Options** dialog box can be used to generate a test certificate to sign a form template. The test certificate should be used to sign form templates for testing only. Test certificates should not be used to sign form templates that will be distributed publicly. Because the certificates are not issued by a Certificate Authority whose root certificate is already trusted on a user's computer, the test certificate will not validate correctly on the user's computer. If you deploy a form template signed with a test certificate, users of your form template will most likely be unable to open it. 
  
## <a name="establishing-a-trusted-root-certificate-and-publisher"></a>创建受信任的根证书和发布者

 用于对表单模板进行签名的证书的受信任根证书必须位于客户端计算机上的受信任根证书存储区内。否则，将无法验证表单模板的发布者，并且表单模板用户将无法使用用于信任发布者的选项。如果受信任根证书位于受信任的根证书存储区内，但受信任的发布者列表中不包含相应的发布者，则系统会提示用户并提供用于信任表单模板发布者的选项。 
  
> [!NOTE]
> 如果已签名的表单模板请求"域"或"受限"访问权限，InfoPath 将使用该签名来验证在签署该表单模板后，它是否已被篡改。并且还会使用该签名确定能否自动更新该表单模板。 
  
## <a name="deploying-signed-form-templates-with-full-trust-access"></a>部署具有完全信任访问权限的已签名表单模板

部署已签名的表单模板的主要方案是在完全信任的表单中启用自动更新等类似域的功能。请求完全信任访问权限的已签名表单模板与 *完全信任的表单*  具有相同的系统资源访问权限。有关完全信任的表单的工作方式以及如何创建和部署这些表单的详细讨论，请参阅 [了解完全信任的表单](understanding-fully-trusted-forms.md)。
  
但是，根据贵组织的计算环境，您可能更愿意使用已签名的表单模板或完全信任的表单。例如，不使用已注册的完全信任表单，而是使用请求"完全信任"访问权限的已签名表单模板会带来一些好处。请求"完全信任"访问权限的已签名表单模板具有以下优点：
  
- 与未签名的完全信任的表单模板不同，无需对其进行注册。
    
- 表单模板能够以静默方式自动更新。
    
由于不必注册请求"完全信任"访问权限的已签名表单模板，因此无需使用安装程序包或脚本文件来部署该模板。该好处极大地简化了完全信任的表单模板的部署过程。
  
在更新请求"完全信任"访问权限的已签名表单模板时，可以只向用户发送更新的模板或在共享位置更新该模板。当用户打开该更新模板时，不会出现提示，并且更新版本将以静默方式覆盖用户计算机上的较旧副本。
  
如果要更新未签名的完全信任表单，则必须对该表单重新打包并重新注册它。此外，已安装的现有完全信任的表单模板只对本地计算机路径起作用，而对网络路径不起作用，这是因为注册过程不支持将本地计算机路径更改为网络路径。但是，因为需要证书才能对表单模板进行签名，所以，如果您不想购买证书，可以选择部署经过注册的完全信任的表单模板。
  
## <a name="deploying-signed-form-templates-with-domain-or-restricted-access"></a>部署具有"域"或"受限"访问权限的已签名的表单模板

具有"域"或"受限"安全级别的已签名表单模板还具有自动更新功能。例如，可以将已签名的表单模板发布到运行 Microsoft SharePoint Foundation 的服务器或具有"域"安全级别的服务器上的文档库。在共享位置更新该表单模板时，用户将自动获得更新的副本。
  

