---
title: 在 InfoPath 表单中进行数字签名
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 7b396d9f-9a47-3170-367f-5d1f0144f927
description: 数字签名是宏或文档中使用的基于加密的安全电子身份验证戳。有效的数字签名可确保数据是来自签名人，并且自签名后未发生更改。在对文档或文档中的特定数据进行签名时，将会对签名进行计算并将其添加到文档中。这样，签名就会与签名数据如影相随了。
ms.openlocfilehash: 6c1f5a1c14c15bc88839dc44d9a5a595d8b52893
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300243"
---
# <a name="digitally-signing-data-in-infopath-forms"></a>在 InfoPath 表单中进行数字签名

数字签名是宏或文档中使用的基于加密的安全电子身份验证戳。有效的数字签名可确保数据是来自签名人，并且自签名后未发生更改。在对文档或文档中的特定数据进行签名时，将会对签名进行计算并将其添加到文档中。这样，签名就会与签名数据如影相随了。
  
为了对数据进行签名，用户需要从证书颁发机构那里申请一个证书，然后使用该证书创建数字签名。证书颁发机构负责管理加密数据所需的证书和密钥（公钥或私钥）的生命周期，并创建签名。
  
以后使用同一文档的用户必须验证现有签名，并根据验证结果，添加自己的贡献并进行签名。为了获得准确的验证结果，验证者必须信任最初用于对文档进行签名的证书的证书颁发机构。
  
XML 数字签名设计用于涉及 XML 文档和数据的事务。XML 签名的强大功能在于它能够只对 XML 文档中的特定数据进行签名。
  
## <a name="types-of-digital-signatures-in-infopath-forms"></a>InfoPath 表单数字签名的类型

Microsoft InfoPath 实现了数字签名，以帮助保护 InfoPath 表单中数据的安全。InfoPath 中共有两种数字签名：
  
- 可确保表单模板（.xsn 文件）的数据完整性和真实性的数字签名
    
- 可确保 XML 表单中数据的完整性和真实性，并支持这些数据的不可否认性的数字签名
    
虽然第一类签名针对的是表单模板（.xsn 文件），第二类签名针对的是用户在 InfoPath 表单文件（.xml 文件）中输入的实际数据，但表单设计者可以允许用户为整个表单或表单的某些部分创建数字签名。签名模板和签名表单之间有着根本性的不同。尽管本文档对签名模板有所提及（作为创建完全信任表单的替代方法），但本文档不提供有关此类签名的详细信息。有关如何对表单模板进行签名的详细信息，请参阅[部署已签署的 InfoPath 表单模板](deploying-signed-infopath-form-templates.md)。本主题重点介绍如何使用签名的 InfoPath XML 表单。由 InfoPath 创建的、用于对 XML 表单中的数据进行签名的数字签名符合 W3C XML 数字签名规范。 
  
## <a name="digital-signatures-features"></a>数字签名功能

InfoPath 提供了一项扩展的数字签名功能，表单开发人员可以设计灵活的表单，以便为整个表单或表单中的特定数据启用数字签名。由于对整个表单进行数字签名总是会创建整个表单的副署，因此对 InfoPath 表单的某些部分进行签名可以更灵活地选择添加到同一数据组中的各个签名之间的关系的种类：可以存在共同签署、副署，或者只允许一个签名。
  
通过签名，InfoPath 默认情况下还会添加一些不可否认性信息，以标识用户在当前视图中看到的数据，以及在创建签名时设置的时间和其他环境设置。可以对不可否认性信息进行自定义，但只有默认不可否认节点中的数据才会显示在不可否认对话框中。
  
若要添加签名，用户必须选择要签名的数据组。可签名的数据组是由表单模板设计者定义的，并用于在填写表单时对数据进行签名。对于每个签名，用户都必须按照数字签名向导选择一个可签名数据组，再选择一个证书，添加注释，然后批准签名并将签名提交到表单。
  
当用户将光标停留在包含已签名数据的控件上时，InfoPath 会显示一个可视指示，说明该数据已经过签名并且无法更改。表单模板设计者可以选择在视图中显示签名以及已签名的数据，以便用户可以轻松访问不可否认性信息。
  
## <a name="programmatic-support-for-digital-signatures"></a>对数字签名的编程支持

InfoPath 对象模型包含对数字签名的支持，这使得开发人员能够以编程方式通过 [SignedDataBlockCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlockCollection.aspx) 类访问表单中定义的可签名数据组，通过 [SignatureCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.aspx) 类访问分配给每个已签名数据组的签名，以及通过 [Certificate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Certificate.aspx) 类访问用于创建签名的证书。此外，在完全信任的表单中， [Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Sign.aspx) 事件处理程序也是可自定义的，这就为在 InfoPath 表单中高级处理数字签名提供了支持。 
  
## <a name="interoperability"></a>互操作性

InfoPath 中的数字签名的基础架构是利用 MSXML5 中支持的数字签名设计的，因此 InfoPath 数字签名与 MSXML5 数字签名具有完全的互操作性。
  
已签名的 InfoPath 表单和 InfoPath 创建的数字签名还将提供与使用 Microsoft .NET Framework（从版本 1.1 开始）创建的数字签名的完全互操作性。InfoPath 创建的签名可以通过使用 .NET Framework 签名验证类的应用程序进行验证。InfoPath 的数字签名机制可成功验证通过使用 .NET Framework 数字签名类设计的应用程序为 InfoPath 表单中包含的数据创建的签名。
  
## <a name="see-also"></a>另请参阅



[使用数字签名](how-to-work-with-digital-signatures.md)

