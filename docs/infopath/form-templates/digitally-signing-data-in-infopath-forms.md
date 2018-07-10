---
title: 在 InfoPath 表单中进行数字签名
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 7b396d9f-9a47-3170-367f-5d1f0144f927
description: 数字签名是宏或文档中使用的基于加密的安全电子身份验证戳。有效的数字签名可确保数据是来自签名人，并且自签名后未发生更改。在对文档或文档中的特定数据进行签名时，将会对签名进行计算并将其添加到文档中。这样，签名就会与签名数据如影相随了。
ms.openlocfilehash: dc839d0751d2e7aeb6f9eaccc3a86ce95e5228e2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773963"
---
# <a name="digitally-signing-data-in-infopath-forms"></a><span data-ttu-id="4726b-106">在 InfoPath 表单中进行数字签名</span><span class="sxs-lookup"><span data-stu-id="4726b-106">Digitally Signing Data in InfoPath Forms</span></span>

<span data-ttu-id="4726b-p102">数字签名是宏或文档中使用的基于加密的安全电子身份验证戳。有效的数字签名可确保数据是来自签名人，并且自签名后未发生更改。在对文档或文档中的特定数据进行签名时，将会对签名进行计算并将其添加到文档中。这样，签名就会与签名数据如影相随了。</span><span class="sxs-lookup"><span data-stu-id="4726b-p102">A digital signature is an electronic, encryption-based, secure stamp of authentication on a macro or document. A valid digital signature confirms that the data originated from the signer and has not been altered since it was signed. When documents or certain data in the documents are signed, the signature is computed and added to the document. This way, the signatures will always travel with the signed data.</span></span>
  
<span data-ttu-id="4726b-p103">为了对数据进行签名，用户需要从证书颁发机构那里申请一个证书，然后使用该证书创建数字签名。证书颁发机构负责管理加密数据所需的证书和密钥（公钥或私钥）的生命周期，并创建签名。</span><span class="sxs-lookup"><span data-stu-id="4726b-p103">In order to sign data, users need to request a certificate from a certificate authority, and then use it to create digital signatures. The certificate authority will manage the life cycle of the certificates and keys (public or private) needed to encrypt data and create the signature.</span></span>
  
<span data-ttu-id="4726b-p104">以后使用同一文档的用户必须验证现有签名，并根据验证结果，添加自己的贡献并进行签名。为了获得准确的验证结果，验证者必须信任最初用于对文档进行签名的证书的证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="4726b-p104">Subsequent users of the document will have to verify existing signatures, and according to the result of the verification, may add their own contribution and sign. For accurate verification results, the verifier must trust the certificate authority who issued the certificate that was used to originally sign the document.</span></span>
  
<span data-ttu-id="4726b-p105">XML 数字签名设计用于涉及 XML 文档和数据的事务。XML 签名的强大功能在于它能够只对 XML 文档中的特定数据进行签名。</span><span class="sxs-lookup"><span data-stu-id="4726b-p105">XML digital signatures are designed for transactions that involve XML documents and data. The power of XML signatures stays in the ability to sign only specific data in an XML document.</span></span>
  
## <a name="types-of-digital-signatures-in-infopath-forms"></a><span data-ttu-id="4726b-117">InfoPath 表单数字签名的类型</span><span class="sxs-lookup"><span data-stu-id="4726b-117">Types of Digital Signatures in InfoPath Forms</span></span>

<span data-ttu-id="4726b-p106">Microsoft InfoPath 实现了数字签名，以帮助保护 InfoPath 表单中数据的安全。InfoPath 中共有两种数字签名：</span><span class="sxs-lookup"><span data-stu-id="4726b-p106">Microsoft InfoPath implements digital signatures to help secure data in InfoPath forms. Two kinds of digital signatures are featured in InfoPath:</span></span>
  
- <span data-ttu-id="4726b-120">可确保表单模板（.xsn 文件）的数据完整性和真实性的数字签名</span><span class="sxs-lookup"><span data-stu-id="4726b-120">Digital signatures that ensure the data integrity and authenticity of the form template (.xsn file)</span></span>
    
- <span data-ttu-id="4726b-121">可确保 XML 表单中数据的完整性和真实性，并支持这些数据的不可否认性的数字签名</span><span class="sxs-lookup"><span data-stu-id="4726b-121">Digital signatures that ensure the integrity, authenticity, and support for non-repudiation related to data in XML forms</span></span>
    
<span data-ttu-id="4726b-p107">虽然第一类签名针对的是表单模板（.xsn 文件），第二类签名针对的是用户在 InfoPath 表单文件（.xml 文件）中输入的实际数据，但表单设计者可以允许用户为整个表单或表单的某些部分创建数字签名。签名模板和签名表单之间有着根本性的不同。尽管本文档对签名模板有所提及（作为创建完全信任表单的替代方法），但本文档不提供有关此类签名的详细信息。有关如何对表单模板进行签名的详细信息，请参阅[部署已签署的 InfoPath 表单模板](deploying-signed-infopath-form-templates.md)。本主题重点介绍如何使用签名的 InfoPath XML 表单。由 InfoPath 创建的、用于对 XML 表单中的数据进行签名的数字签名符合 W3C XML 数字签名规范。</span><span class="sxs-lookup"><span data-stu-id="4726b-p107">Whereas the first category of signatures is targeting the form template (.xsn file), the second category targets the actual user-entered data in InfoPath form files (.xml files), where the form designer can enable users to create digital signatures for the whole form or for sections of the form. There are fundamental differences between a signed template and a signed form. Although this document will have some references to signed templates (as an alternative way to create a form that will run as fully trusted), it does not provide details about this kind of signing. For more information about how to sign form templates, see [Deploying Signed InfoPath Form Templates](deploying-signed-infopath-form-templates.md) The focus in this topic is using signed InfoPath XML forms. Digital signatures created by InfoPath to sign data in XML forms comply with W3C XML Digital Signatures specifications.</span></span> 
  
## <a name="digital-signatures-features"></a><span data-ttu-id="4726b-127">数字签名功能</span><span class="sxs-lookup"><span data-stu-id="4726b-127">Digital Signatures Features</span></span>

<span data-ttu-id="4726b-p108">InfoPath 提供了一项扩展的数字签名功能，表单开发人员可以设计灵活的表单，以便为整个表单或表单中的特定数据启用数字签名。由于对整个表单进行数字签名总是会创建整个表单的副署，因此对 InfoPath 表单的某些部分进行签名可以更灵活地选择添加到同一数据组中的各个签名之间的关系的种类：可以存在共同签署、副署，或者只允许一个签名。</span><span class="sxs-lookup"><span data-stu-id="4726b-p108">InfoPath offers an extended digital signatures feature, with template developers being able to design flexible forms that enable digital signatures either for the whole form or for specific data in the form. Whereas digitally signing the whole form will always create counter-signatures for the form as an entity, signing parts of InfoPath forms enables more flexibility in choosing the kind of relationship between signatures added to the same set of data: there can be co-signatures, counter-signatures, or only one signature allowed.</span></span>
  
<span data-ttu-id="4726b-p109">通过签名，InfoPath 默认情况下还会添加一些不可否认性信息，以标识用户在当前视图中看到的数据，以及在创建签名时设置的时间和其他环境设置。可以对不可否认性信息进行自定义，但只有默认不可否认节点中的数据才会显示在不可否认对话框中。</span><span class="sxs-lookup"><span data-stu-id="4726b-p109">With the signature, InfoPath will also add by default some non-repudiation information to identify the data users have seen in the current view, as well as the time and other environment settings as they were set when the signature was created. The non-repudiation information can be customized, but only the data in default non-repudiation nodes will be displayed in the non-repudiation dialog.</span></span>
  
<span data-ttu-id="4726b-p110">若要添加签名，用户必须选择要签名的数据组。可签名的数据组是由表单模板设计者定义的，并用于在填写表单时对数据进行签名。对于每个签名，用户都必须按照数字签名向导选择一个可签名数据组，再选择一个证书，添加注释，然后批准签名并将签名提交到表单。</span><span class="sxs-lookup"><span data-stu-id="4726b-p110">In order to add a signature, users have to select the set of data that will be signed. The set of data that can be signed is defined by the form template designer and used to sign the data when filling out the form. For each signature, users will have to follow a digital signature wizard for selecting the set of signable data, selecting a certificate, adding comments, and approving and committing the signature to the form.</span></span>
  
<span data-ttu-id="4726b-p111">当用户将光标停留在包含已签名数据的控件上时，InfoPath 会显示一个可视指示，说明该数据已经过签名并且无法更改。表单模板设计者可以选择在视图中显示签名以及已签名的数据，以便用户可以轻松访问不可否认性信息。</span><span class="sxs-lookup"><span data-stu-id="4726b-p111">When a user rests the mouse over a control that contains signed data, InfoPath displays a visual indication that the data is signed and cannot be changed. Form template designers can choose to have the signatures displayed in the view with the signed data so that users can take advantage of easy access to the non-repudiation information.</span></span>
  
## <a name="programmatic-support-for-digital-signatures"></a><span data-ttu-id="4726b-137">对数字签名的编程支持</span><span class="sxs-lookup"><span data-stu-id="4726b-137">Programmatic Support for Digital Signatures</span></span>

<span data-ttu-id="4726b-p112">InfoPath 对象模型包含对数字签名的支持，这使得开发人员能够以编程方式通过 [SignedDataBlockCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlockCollection.aspx) 类访问表单中定义的可签名数据组，通过 [SignatureCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.aspx) 类访问分配给每个已签名数据组的签名，以及通过 [Certificate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Certificate.aspx) 类访问用于创建签名的证书。此外，在完全信任的表单中， [Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Sign.aspx) 事件处理程序也是可自定义的，这就为在 InfoPath 表单中高级处理数字签名提供了支持。</span><span class="sxs-lookup"><span data-stu-id="4726b-p112">The InfoPath object model includes support for digital signatures, which enables developers programmatic access to the sets of signable data are defined in the form through the [SignedDataBlockCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlockCollection.aspx) class, to the signatures assigned to each set of signed data through the [SignatureCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.aspx) class, and to the certificate that is used to create a signature through the [Certificate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Certificate.aspx) class. Additionally, the [Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Sign.aspx) event handler is customizable in fully trusted forms, offering support for advanced processing of digital signatures in InfoPath forms.</span></span> 
  
## <a name="interoperability"></a><span data-ttu-id="4726b-140">互操作性</span><span class="sxs-lookup"><span data-stu-id="4726b-140">Interoperability</span></span>

<span data-ttu-id="4726b-141">InfoPath 中的数字签名的基础架构是利用 MSXML5 中支持的数字签名设计的，因此 InfoPath 数字签名与 MSXML5 数字签名具有完全的互操作性。</span><span class="sxs-lookup"><span data-stu-id="4726b-141">The infrastructure for digital signatures in InfoPath was designed by using the digital signatures support in MSXML5 so that InfoPath digital signatures have full interoperability with MSXML5 digital signatures.</span></span>
  
<span data-ttu-id="4726b-p113">已签名的 InfoPath 表单和 InfoPath 创建的数字签名还将提供与使用 Microsoft .NET Framework（从版本 1.1 开始）创建的数字签名的完全互操作性。InfoPath 创建的签名可以通过使用 .NET Framework 签名验证类的应用程序进行验证。InfoPath 的数字签名机制可成功验证通过使用 .NET Framework 数字签名类设计的应用程序为 InfoPath 表单中包含的数据创建的签名。</span><span class="sxs-lookup"><span data-stu-id="4726b-p113">Signed InfoPath forms and digital signatures created by InfoPath will also provide full interoperability with digital signatures created by using the Microsoft .NET Framework (starting with version 1.1). Signatures created by InfoPath can be verified by applications that use .NET Framework signature verification classes. Signatures created for data hosted in InfoPath forms by applications designed using .NET Framework digital signatures classes are successfully verified by InfoPath's digital signatures mechanism.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4726b-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4726b-145">See also</span></span>



[<span data-ttu-id="4726b-146">使用数字签名</span><span class="sxs-lookup"><span data-stu-id="4726b-146">Work with Digital Signatures?</span></span>](how-to-work-with-digital-signatures.md)

