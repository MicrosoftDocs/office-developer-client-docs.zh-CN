---
title: 开发 InfoPath 表单的安全指南
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4690028e-20ac-297b-4651-801f5159c747
description: 阅读本主题之前，请先参阅 更多 InfoPath 表单安全性概念，以便对 InfoPath 安全模型有一个大概了解。
ms.openlocfilehash: 5108d8b1967b72ac4805f892bcf3bbae3aecccbe
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299921"
---
# <a name="security-guidelines-for-developing-infopath-forms"></a>开发 InfoPath 表单的安全指南

阅读本主题之前，请先参阅 [更多 InfoPath 表单安全性概念](additional-infopath-form-security-concepts.md)，以便对 InfoPath 安全模型有一个大概了解。 
  
## <a name="security-issues-for-users-of-infopath-forms"></a>InfoPath 表单用户关注的安全问题

Microsoft InfoPath 用户所关注的主要安全问题与在 Internet Explorer 中运行的 Web 应用程序所面临的问题类似。但是应当注意，为表单提供的安全级别只取决于表单模板所在的位置，而与用户在何处存储或打开其创建的结果 XML 文档无关。用户可以通过查看 InfoPath 中的状态栏，判断正在使用的表单模板的位置。
  
InfoPath 可帮助用户抵御由恶意编写的表单模板所引发的下列潜在威胁：
  
- 可能泄露本地计算机或远程数据源中的敏感信息。
    
- 恶意使用 ActiveX 控件。
    
- 恶意使用 InfoPath 对象模型中的属性和方法。
    
## <a name="disclosure-of-sensitive-information"></a>泄露敏感信息

如果某个恶意表单编写者创建了一个表单，该表单利用当前用户的安全凭据访问某个域上的数据源，而该域并非部署该表单所在的域，这时，就会发生最为常见的敏感信息泄露情况。 例如，一个恶意用户可能通过电子邮件或使用 URL（指向私人共享或 Web 服务器上的表单）发送一个表单。 该表单中可能含有脚本，该脚本利用当前用户的凭据执行数据访问请求，从该恶意用户原本无权访问的另一个域中的数据源（例如薪资或其他敏感信息的数据库）中检索数据。 此类安全风险情况被称为跨域访问数据。
  
InfoPath 建立在 Internet Explorer 安全模型基础之上。该模型提供了一项称为“跨域访问数据源”**** 的设置，默认情况下，该设置禁止对位于“Internet”**** 和“受限制的站点”**** 安全区域内的 InfoPath 表单执行跨域访问。此外，该设置还提示用户允许或禁止对位于“本地 Intranet”**** 安全区域内的 InfoPath 表单执行跨域访问，它允许对位于“受信任的站点”**** 或“本地计算机”**** 区域内的 InfoPath 表单执行跨域访问。 
  
## <a name="malicious-use-of-activex-controls"></a>恶意使用 ActiveX 控件

当恶意表单编写者针对可访问文件系统的 ActiveX 控件编写代码，以检索个人文件和密码列表、删除文件或禁用用户的系统时，主要就会发生恶意使用 ActiveX 控件的情况。InfoPath 表单只能通过业务逻辑或在任务窗格中运行的脚本来运行针对 ActiveX 控件的代码。InfoPath 不允许 InfoPath 视图中的脚本运行 ActiveX 控件。
  
The Internet Explorer security model that InfoPath is built upon provides a setting called **Initialize and script ActiveX controls marked as unsafe**. This setting, by default, disables initializing and scripting ActiveX controls marked as unsafe for InfoPath forms that reside in the **Local intranet**, **Internet**, and **Restricted sites** security zones. It prompts the user to allow or disallow scripting of ActiveX controls marked as unsafe for InfoPath forms that reside in the **Trusted sites** or the **Local Machine** security zones, and it enables scripting of ActiveX controls marked as unsafe for InfoPath forms that are fully trusted. 
  
此外，无论您位于哪个安全区域，也无论表单的信任级别如何，在设计模式下，您都无法在控件任务窗格中插入那些标记为不能安全地进行初始化和编写脚本的 ActiveX 控件。
  
## <a name="malicious-use-of-infopath-object-model-code"></a>恶意使用 InfoPath 对象模型代码

同样，通过代码调用的 InfoPath 方法和属性可带来不同程度的风险。例如，可以使用 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.SaveAs.aspx) 类的 [SaveAs(String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 方法在文件系统的任何位置写入数据。为了有助于防止恶意使用这些对象模型成员，InfoPath 对象模型实施了三级安全防护，以确定如何及在何处使用特定的对象模型成员。有关该功能的详细信息，请参阅 [关于具有代码的表单模板的安全模型](about-the-security-model-for-form-templates-with-code.md)。
  
## <a name="best-practices-for-developers-of-infopath-forms"></a>针对 InfoPath 表单开发人员的最佳实践

创建 InfoPath 表单的开发人员应知道如何实施下列最佳安全实践：
  
- 如何识别与表单关联的 XML 文件中潜藏的安全问题。
    
- 如何避免向表单用户呈现令人费解或讨厌的错误消息。
    
- 如何对 ActiveX 控件的 CAB 文件进行签名。
    
- 如何对以电子邮件附件形式发送的表单模板进行签名。
    
## <a name="best-practices-for-xml-data-associated-with-a-form"></a>与表单关联的 XML 数据的最佳做法

请注意，可以从任何来源向 InfoPath 表单馈送 XML 数据，包括那些用户不一定信任或控制的来源。 例如，InfoPath 可以从网页链接中获取 XML 数据，或者从通过电子邮件发送给用户的 XML 附件中获取 XML 数据。 若要缓和这些风险，请注意以下最佳做法：
  
- 不要将从 XML 读取的不可信数据传递给任务窗格的 Microsoft JScript **eval()** 函数或 **innerHTML** 属性。这两种调用都可能用于执行恶意脚本。在任务窗格中，应使用 **innerText** 属性来替代。请注意，InfoPath 视图无法执行脚本。 
    
- 如果来自 XML 文件的数据未经验证便提交给数据库，则会给数据库带来安全风险。
    
如果未对数据进行验证便将其提交给数据源，则会破坏数据源中数据的完整性，或更有甚者，有可能造成缓冲区数据溢出。另外，如果您试图直接在服务器上使用不可信数据，则可能导致脚本注入或 SQL 注入。
  
## <a name="best-practices-to-avoid-presenting-confusing-error-messages"></a>避免呈现令人费解的错误消息的最佳实践

 **将表单及其数据源部署在同一域中**
  
The security risk of cross-domain data access is not clearly understood by most users. Deploying forms that continually warn and prompt users about allowing cross-domain data access has the effect of training many users to approve all cross-domain access requests, or to add the originating domain to their **Trusted sites** list, without taking the security risks seriously. To avoid this situation, deploy InfoPath forms on the same server as any data sources on which they depend. 
  
 **避免使用那些没有标记为可安全编写脚本的 ActiveX 控件**
  
ActiveX 控件或许会公开可被用来损害用户系统的属性和方法（如用于访问计算机文件系统的方法）。应尽可能只使用那些标记为可安全编写脚本的 ActiveX 控件。这些控件已经过测试，可以确保无论网页的脚本如何操纵控件的方法和属性，都不会损害用户系统或危害用户安全。同样，在创建与 InfoPath 结合使用的 ActiveX 控件时，应检查相关代码，并对 ActiveX 控件进行严格测试，然后才将其标记为可安全编写脚本。
  
InfoPath 使用基于 Internet Explorer 安全区域的安全模型。因此，InfoPath 表单将使用与 Internet Explorer 相同的权限。默认情况下，这些权限允许在不提示用户的情况下对标记为可安全编写脚本的 ActiveX 控件进行脚本调用。
  
## <a name="best-practices-for-managing-the-cab-files-of-activex-controls"></a>管理 ActiveX 控件的 CAB 文件的最佳实践

ActiveX 控件可位于专为 InfoPath 编辑器设计的表单模板中。表单模板 (.xsn) 文件中必须包括用户计算机上尚不存在的这些控件的 CAB 文件。表单模板中包含的 CAB 文件必须经过数字签名方能安装。无论信任级别或安全区域如何设置，InfoPath 都不会安装未经签名的 CAB 文件。
  
为了确保能够验证 CAB 文件上的数字签名，应使用特定证书签署文件，该证书应包含指向已获得信任的证书根的信任链。否则，签名无法通过身份验证，签名验证将失败，CAB 文件也将无法安装。
  
## <a name="best-practices-for-form-templates-sent-as-an-attachment-to-an-email-message"></a>针对以电子邮件附件形式发送的表单模板的最佳做法

InfoPath 支持将表单模板部署为电子邮件的附件并将表单模板从一个位置移到另一个位置。 对你设计并打算部署为电子邮件附件的表单模板进行数字签名是一个很好的安全做法。 电子邮件邮件部署的表单模板上的数字签名不仅可以确保该模板的真实性， 还具有允许表单模板自动更新的额外好处。
  
应使用特定证书签署表单模板，该证书应包含指向已获得信任的证书根的信任链。如果不使用此类证书进行签名，则会因签名无法通过身份验证而导致签名验证失败。
  
> [!NOTE]
> 如果已签名的表单模板请求域访问或受限制的访问，则 InfoPath 除了确定它能否自动更新模板外，将不会检查或验证签名。 
  
有关电子邮件部署的详细信息，请参阅[安全级别、电子邮件部署和远程表单模板](security-levels-email-deployment-and-remote-form-templates.md)。
  

