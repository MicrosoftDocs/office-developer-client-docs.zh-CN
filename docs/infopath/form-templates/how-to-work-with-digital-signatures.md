---
title: 使用数字签名
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- digital signatures [infopath 2007],InfoPath 2007, digital signatures
localization_priority: Normal
ms.assetid: fd13fb71-aecf-47bb-8a6b-db70bd90ceeb
description: Microsoft.Office.InfoPath 命名空间的对象模型提供了以编程方式使用数字签名的功能。
ms.openlocfilehash: ea657f80f6e38a06a91e19c245eadc203c7c580c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425573"
---
# <a name="work-with-digital-signatures"></a>使用数字签名

[Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间的对象模型提供了以编程方式使用数字签名的功能。 
  
## <a name="digital-signature-features"></a>数字签名功能

通过 InfoPath 提供的数字签名功能，您可以： 
  
- 为整个表单启用签名，或者为表单中可单独签名的特定数据集启用签名。
    
- 对于可签名的每一个数据集，指定允许单个还是多个签名，并指定它们之间的关系。例如，可以指定它们是否是并行联署，以及每个新的签名是否都副署所有更早的签名。
    
- 指定当表单用户签署表单时将显示给表单用户的消息。
    
- 在文档中插入和查看签名。 
    
- View verifiable non-repudiation information that has been added to each signature for increased security. This additional information, which includes a view of the form as it was presented to each signer, is part of the signature and cannot be removed without invalidating the signature. At any time, you can recall this data by clicking on the signature in the form to display the **Verify Digital Signature** dialog box. 
    
- 利用对象模型来处理数字签名。通过数字签名对象模型来将自定义信息添加到完全信任表单中的签名块。 
    
## <a name="overview-of-the-digital-signatures-object-model"></a>数字签名对象模型概述

### <a name="the-sign-event"></a>Sign 事件

数字签名对象模型提供以下事件。
  
|**名称**|**说明**|
|:-----|:-----|
|[Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Sign.aspx) <br/> |在选择要签名的数据组之后发生。  <br/> 可以使用此事件处理数字签名中存储的数据。例如，可以添加受信任时间戳服务器中的数据，也可以添加事务的服务器端副署。此外，如果当前用户不是特定组的成员，还可以使用此事件阻止签名。  <br/> |
   
### <a name="the-signeventargs-object"></a>SignEventArgs 对象

[Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Sign.aspx) 事件的事件处理程序可以处理 [SignEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignEventArgs.aspx) 事件对象，该对象提供下列属性。 
  
|**名称**|**说明**|
|:-----|:-----|
|[SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignEventArgs.SignedDataBlock.aspx) <br/> |获取引发 [Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Sign.aspx) 事件的数据组。  <br/> |
|[SignatureWizard](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignEventArgs.SignatureWizard.aspx) <br/> |获取或设置是否显示****“数字签名”对话框。  <br/> |
   
> [!NOTE]
> 在随 InfoPath 2003 一起提供的 [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 托管代码对象模型中， [OnSign](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignEvent.aspx) 事件的 [SignEvent](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2.OnSign.aspx) 事件对象提供了一个 **XDocument** 属性，用来访问与该事件关联的表单的 **XDocument** 对象。这对于通过 InfoPath Forms Services 或 InfoPath 使用 [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 对象模型创建的表单模板并不是必需的，这是因为可以使用 [this](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) (C#) 或 **Me** (Visual Basic) 关键字在表单代码中访问 **XmlForm** 类的对象模型成员。例如，若要访问 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Signed.aspx) 类的 [Signed](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 属性以确定某个表单是否经过签名，您可以键入  `this.Signed` 或  `Me.Signed.`。
  
### <a name="collections-and-objects"></a>集合和对象

数字签名对象模型提供下列集合。
  
|**名称**|**说明**|
|:-----|:-----|
|[SignedDataBlockCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlockCollection.aspx) <br/> |设计时在 InfoPath 设计模式下定义的表单模板中的 [SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) 对象的集合。  <br/> [SignedDataBlockCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlockCollection.aspx) 集合实现了可用于访问与表单关联的 [SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) 对象的属性。可以通过 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlockCollection.aspx) 类的 [SignedDataBlocks](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.SignedDataBlocks.aspx) 属性来访问与表单关联的 [SignedDataBlockCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 对象。  <br/> |
|[SignatureCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.aspx) <br/> |对于表单中的每个 [SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.aspx) 对象，都包含 [Signature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) 对象的集合。  <br/> [SignatureCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.aspx) 类实现一些属性和一个方法，可用于访问与表单关联的 [Signature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.aspx) 对象以及用于创建签名。可以使用 [Signatures](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.aspx) 属性访问与 [SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) 关联的 [SignatureCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.Signatures.aspx) 对象。  <br/> 在使用 [SignatureCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.CreateSignature.aspx) 类的 [CreateSignature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.aspx) 方法时，请记住，在对 [Signature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.Sign.aspx) 对象调用 [Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.aspx) 方法之前不会写入签名。只能通过完全信任的表单模板的 **Sign** 事件处理程序来调用这些方法。  <br/> |
   
数字签名对象模型提供下列对象。
  
|**名称**|**说明**|
|:-----|:-----|
|[SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) <br/> |表示表单中的一组可签名数据。[SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) 对象提供很多属性和一个方法，可用于以编程方式与一组可签名数据进行交互。<br/> |
|[Signature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.aspx) <br/> |表示已添加到表单或表单中的一组可签名数据的数字签名。[Signature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.aspx) 对象实现可用于检索有关数字签名的信息的属性，以及用于编写 XML 数字签名块并计算其加密哈希值的 [Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.Sign.aspx) 方法。<br/> |
|[Certificate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Certificate.aspx) <br/> |代表用来创建签名的 X.509 数字证书。  <br/> |
   
## <a name="working-with-digital-signatures-programmatically"></a>以编程方式处理数字签名

[Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间的对象模型提供了以编程方式与数字签名进行交互的成员。特别是，根据以下时间线，在提交签名块之前，完全信任的表单可以向其添加自定义信息： 
  
1. 用户选择向表单添加数字签名。
    
2. 显示“数字签名”**** 对话框，用户单击“添加”****，然后选择要签署的数据。
    
3. 引发由 [SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Sign.aspx) 对象代表的选定数据的 [Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) 事件，并执行 [SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.Sign.aspx) 对象的 [Sign()](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) 方法以及 [SignatureCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.CreateSignature.aspx) 集合的 [CreateSignature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.aspx) 方法。 
    
4. 执行任何可选的自定义操作。
    
5. 执行 [Signature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.Sign.aspx) 对象的 [Sign()](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.aspx) 方法。 
    
6. 显示“签名”**** 对话框，用来键入一个名称（或选择一个签名图像），选择签名时使用的证书以及输入注释。 
    
7. 单击“签名”**** 按钮时，签名将添加到表单的签名集合中，并且将捕获认可信息并与签名一起保存（以后可通过单击“数字签名”**** 对话框中的“查看签名的表单”****，然后单击“查看收集的附加签名信息”**** 来查看）。
    
下面的示例在用户签署所选数据时调用 [Sign()](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.Sign.aspx) 方法，并利用从受信任的时间戳服务中检索的时间戳值来副署签名。 
  
```cs
public void FormEvents_Sign(object sender, SignEventArgs e)
{
   // Add a new Signature object to the SignedDataBlockCollection.
   Signature thisSignature = 
      e.SignedDataBlock.Signatures.CreateSignature();
   // Write the XML digital signature block and compute hash
   // for signed data.
   thisSignature.Sign();
   // Countersign the signature with a trusted timestamp.
   // Get the XML node storing the signature block.
   XPathNavigator oNodeSig = thisSignature.SignatureBlockXmlNode;
   XPathNavigator oNodeSigValue = 
      oNodeSig.SelectSingleNode(
      ".//*[local-name(.)='signatureValue']");
   // Get timestamp from a trusted timestamp service (fictitious).
   MyTrustedTimeStampService s = new MyTrustedTimeStampService();
   string strVerifiedTimeStamp = s.AddTimeStamp(oNodeSigValue.Value);
   // Add the value returned from the timestamp service to the 
   // unsigned part of the signature block.
   XPathNavigator oNodeObj = 
      oNodeSig.SelectSingleNode(".//*[local-name(.)='Object']");
   XPathNavigator oNode = oNodeObj.Clone();
   oNode.SetValue(strVerifiedTimeStamp);
   oNodeObj.MoveToParent();
   oNodeObj.AppendChild(oNode);
   e.SignatureWizard = false;
}
```

```vb
Public Sub FormEvents_Sign(ByVal sender As Object, _
   ByVal e As SignEventArgs)
   ' Add a new Signature object to the SignedDataBlockCollection.
   Dim thisSignature As Signature = 
      e.SignedDataBlock.Signatures.CreateSignature
   ' Write the XML digital signature block and compute hash
   ' for signed data.
   thisSignature.Sign()
   ' Countersign the signature with a trusted timestamp.
   ' Get the XML node storing the signature block
   Dim oNodeSig As XPathNavigator  = _
      thisSignature.SignatureBlockXmlNode
   Dim oNodeSigValue As XPathNavigator  = _
      oNodeSig.SelectSingleNode(_
      ".//*[local-name(.)='signatureValue']")
   ' Get timestamp from a trusted timestamp service (fictitious).
   Dim s As MyTrustedTimeStampService = New MyTrustedTimeStampService()
   Dim strVerifiedTimeStamp As String  = _
      s.AddTimeStamp(oNodeSigValue.Value)
   ' Add the value returned from the timestamp service to the 
   ' unsigned part of the signature block.
   Dim oNodeObj As XPathNavigator  = 
      oNodeSig.SelectSingleNode(".//*[local-name(.)='Object']")
   Dim oNode As XPathNavigator  = oNodeObj.Clone()
   oNode.SetValue(strVerifiedTimeStamp)
   oNodeObj.MoveToParent()
   oNodeObj.AppendChild(oNode)
   e.SignatureWizard = False
```


