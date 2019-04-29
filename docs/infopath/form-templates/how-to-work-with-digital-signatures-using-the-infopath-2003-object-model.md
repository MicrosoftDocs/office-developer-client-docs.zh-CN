---
title: 使用 InfoPath 2003 对象模型处理数字签名
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- 数字签名 [infopath 2007]，infopath 2003 兼容的表单模板，InfoPath 2003 兼容的表单模板，数字签名
localization_priority: Normal
ms.assetid: d6318238-fd45-4854-a3c9-c27c5685bd6b
description: InfoPath 2003 兼容对象模型提供了以编程方式处理数字签名的功能。
ms.openlocfilehash: 86e2c85c7515c896612df09b6186462480ceff61
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433442"
---
# <a name="work-with-digital-signatures-using-the-infopath-2003-object-model"></a>使用 InfoPath 2003 对象模型处理数字签名

InfoPath 2003 兼容的对象模型提供以编程方式处理数字签名的功能。
  
## <a name="digital-signature-features"></a>数字签名功能

利用 InfoPath 中提供的数字签名功能，您可以： 
  
- 为整个表单启用签名，或者为表单中可单独签名的特定数据集启用签名。
    
- 对于可签名的每一个数据集，指定允许单个还是多个签名，并指定它们之间的关系。例如，可以指定它们是否是并行联署，以及每个新的签名是否都副署所有更早的签名。
    
- 指定当表单用户签署表单时将显示给表单用户的消息。
    
- 在文档中插入和查看签名。 
    
- View verifiable non-repudiation information that has been added to each signature for increased security. This additional information, which includes a view of the form as it was presented to each signer, is part of the signature and cannot be removed without invalidating the signature. At any time, you can recall this data by clicking on the signature in the form to display the **Verify Digital Signature** dialog box. 
    
- 利用对象模型来处理数字签名。通过数字签名对象模型来将自定义信息添加到完全信任表单中的签名块。 
    
## <a name="overview-of-the-digital-signatures-object-model"></a>数字签名对象模型概述

### <a name="events"></a>活动

数字签名对象模型提供以下事件。
  
|**名称**|**说明**|
|:-----|:-----|
|[OnSign](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSign.aspx) <br/> |在可签名数据集被选定用于签名之后发生。  <br/> 可以使用此事件处理数字签名中存储的数据。例如，可以添加受信任时间戳服务器中的数据，也可以添加事务的服务器端副署。此外，如果当前用户不是特定组的成员，还可以使用此事件阻止签名。  <br/> |
   
**OnSign** 事件返回对 [SignEventObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignEventObject.aspx) 对象的引用，它提供以下属性。 
  
|**名称**|**说明**|
|:-----|:-----|
|[ReturnStatus](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SignEvent.ReturnStatus.aspx) <br/> |获取或设置一个 **Boolean** 值，指示 **OnSign** 事件的返回状态。  <br/> |
|[SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SignEvent.SignedDataBlock.aspx) <br/> |获取触发了 **OnSign** 事件的签名数据块。  <br/> |
|[XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignEvent.XDocument.aspx) <br/> |获取对与 **OnSign** 事件关联的 **XDocument** 对象的引用。  <br/> |
   
### <a name="collections-and-objects"></a>集合和对象

数字签名对象模型提供下列集合。
  
|**名称**|**说明**|
|:-----|:-----|
|[SignedDataBlocksCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignedDataBlocksCollection.aspx) <br/> |表单模板中 [SignedDataBlockObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignedDataBlockObject.aspx) 对象的集合，如表单定义文件 (.xsf) 中所定义。  <br/> **SignedDataBlocksCollection** 集合实现可用于访问与表单相关联的 **SignedDataBlockObjects** 对象的属性。通过 **XDocument** 对象的 [SignedDataBlocks](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.SignedDataBlocks.aspx) 属性可以访问 [SignedDataBlocks](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) 集合。  <br/> |
|[SignaturesCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignaturesCollection.aspx) <br/> |包含表单中每个 [SignedDataBlockObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignatureObject.aspx) 的 **SignatureObject** 对象的集合。  <br/> **SignaturesCollection** 集合实现一些属性和一个方法，可用于访问表单的关联 **SignatureObject** 对象以及创建签名。通过 **SignedDataBlockObject** 对象可访问它。  <br/> 在使用 [SignaturesCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Signatures.Create.aspx) 集合的 **Create** 方法时，请记住，在 [SignatureObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Signature.Sign.aspx) 对象上调用 **Sign** 方法之前，不会写入签名。只能通过完全信任的表单模板的 **OnSign** 事件处理程序来调用这些方法。  <br/> |
   
数字签名对象模型提供以下对象。
  
|**名称**|**说明**|
|:-----|:-----|
|[SignedDataBlockObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignedDataBlockObject.aspx) <br/> |表示表单中的一组可签名数据。 **SignedDataBlock** 对象提供很多属性和一个方法，可用于以编程方式与一组可签名数据进行交互。  <br/> |
|[SignatureObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignatureObject.aspx) <br/> |表示已添加到表单或表单中的一组可签名数据的数字签名。 **SignatureObject** 集合实现可用于检索有关数字签名的信息的属性，以及实现用于写 XML 数字签名块并计算其加密哈希值的 [Sign](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Signature.Sign.aspx) 方法。  <br/> |
|[CertificateObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.CertificateObject.aspx) <br/> |代表用来创建签名的 X.509 数字证书。  <br/> |
   
## <a name="working-with-digital-signatures-programmatically"></a>以编程方式处理数字签名

InfoPath 2003 兼容对象模型提供了以编程方式与数字签名进行交互的成员。特别是，根据以下时间线，在提交签名块之前，完全信任的表单可以向其添加自定义信息：
  
1. 用户选择向表单添加数字签名。
    
2. 随即会显示“**数字签名向导**”的第一个窗格。 
    
3. 由 **SignedDataBlockObject** 对象代表的选定数据的 **OnSign** 事件被触发，并且执行 **SignedDataBlockObject** 的 **Sign** 方法，以及 **SignaturesCollection** 集合的 **Create** 方法。 
    
4. 执行任何可选的自定义操作。
    
5. 执行 **SignatureObject** 的 **Sign** 方法。 
    
6. 向导的第二和第三个窗格将会显示，供用户选择签名时所用的证书和输入注释。
    
7. 随即显示不可否认信息（稍后可在“**验证数字签名**”对话框中查看）。 
    
8. 点击“**签名**”按钮后，签名将添加到表单的签名集合中。 
    
下面的示例调用“**签名**”对话框并向签名副署一个从受信任的时间戳服务获取的时间戳值。 
  
```cs
[InfoPathEventHandler(EventType=InfoPathEventType.OnSign)]
public void OnSign(SignEvent e)
{
    Signature signature = e.SignedDataBlock.Signatures.Create();
    // Invoke the Sign dialog box to sign the data block.
    signature.Sign();
    // Countersign the signature with a trusted timestamp
    // Get the XML node storing the signature block
    IXMLDOMNode oNodeSig = signature.SignatureBlockXmlNode;
    IXMLDOMNode oNodeSigValue = oNodeSig.selectSingleNode(".//*[local-name(.)='signatureValue']");
    // Get timestamp from a trusted timestamp service (fictitious).
    MyTrustedTimeStampService s = new MyTrustedTimeStampService();
    string strVerifiedTimeStamp = s.AddTimeStamp(oNodeSigValue.text);
    
    //Add the value returned from the timestamp service to the 
    //unsigned part of the signature block
    IXMLDOMNode oNodeObj = oNodeSig.selectSingleNode(".//*[local-name(.)='Object']");
    IXMLDOMNode oNode = oNodeObj.cloneNode(false);
    oNode.text = strVerifiedTimeStamp;
    oNodeObj.parentNode.appendChild(oNode);
    e.ReturnStatus = true;
}
```


