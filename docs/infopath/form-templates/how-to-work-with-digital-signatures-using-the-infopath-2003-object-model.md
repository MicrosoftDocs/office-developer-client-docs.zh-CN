---
title: 使用 InfoPath 2003 对象模型处理数字签名
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- 数字签名 [infopath 2007]，infopath 2003 兼容的表单模板，InfoPath 2003 兼容的表单模板，数字签名
localization_priority: Normal
ms.assetid: d6318238-fd45-4854-a3c9-c27c5685bd6b
description: InfoPath 2003 兼容的对象模型提供以编程方式处理数字签名的功能。
ms.openlocfilehash: 86e2c85c7515c896612df09b6186462480ceff61
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433442"
---
# <a name="work-with-digital-signatures-using-the-infopath-2003-object-model"></a><span data-ttu-id="7a976-104">使用 InfoPath 2003 对象模型处理数字签名</span><span class="sxs-lookup"><span data-stu-id="7a976-104">Work with Digital Signatures Using the InfoPath 2003 Object Model</span></span>

<span data-ttu-id="7a976-105">InfoPath 2003 兼容的对象模型提供以编程方式处理数字签名的功能。</span><span class="sxs-lookup"><span data-stu-id="7a976-105">The InfoPath 2003-compatible object model provides features for working with digital signatures programmatically.</span></span>
  
## <a name="digital-signature-features"></a><span data-ttu-id="7a976-106">数字签名功能</span><span class="sxs-lookup"><span data-stu-id="7a976-106">Digital Signature Features</span></span>

<span data-ttu-id="7a976-107">利用 InfoPath 中提供的数字签名功能，您可以：</span><span class="sxs-lookup"><span data-stu-id="7a976-107">The digital signatures features available in InfoPath enable you to:</span></span> 
  
- <span data-ttu-id="7a976-108">为整个表单启用签名，或者为表单中可单独签名的特定数据集启用签名。</span><span class="sxs-lookup"><span data-stu-id="7a976-108">Enable signatures for the entire form, or for specific sets of data in the form that can be signed separately.</span></span>
    
- <span data-ttu-id="7a976-p101">对于可签名的每一个数据集，指定允许单个还是多个签名，并指定它们之间的关系。例如，可以指定它们是否是并行联署，以及每个新的签名是否都副署所有更早的签名。</span><span class="sxs-lookup"><span data-stu-id="7a976-p101">Specify, for each set of data that can be signed, whether a single signature or multiple signatures are allowed and what their relationship will be. For example, you can specify whether they are parallel co-signatures or whether each new signature countersigns all the earlier signatures.</span></span>
    
- <span data-ttu-id="7a976-111">指定当表单用户签署表单时将显示给表单用户的消息。</span><span class="sxs-lookup"><span data-stu-id="7a976-111">Specify a message to be shown to form users as they sign the form.</span></span>
    
- <span data-ttu-id="7a976-112">在文档中插入和查看签名。</span><span class="sxs-lookup"><span data-stu-id="7a976-112">Insert and see a signature in the document.</span></span> 
    
- <span data-ttu-id="7a976-p102">View verifiable non-repudiation information that has been added to each signature for increased security. This additional information, which includes a view of the form as it was presented to each signer, is part of the signature and cannot be removed without invalidating the signature. At any time, you can recall this data by clicking on the signature in the form to display the **Verify Digital Signature** dialog box.</span><span class="sxs-lookup"><span data-stu-id="7a976-p102">View verifiable non-repudiation information that has been added to each signature for increased security. This additional information, which includes a view of the form as it was presented to each signer, is part of the signature and cannot be removed without invalidating the signature. At any time, you can recall this data by clicking on the signature in the form to display the **Verify Digital Signature** dialog box.</span></span> 
    
- <span data-ttu-id="7a976-p103">利用对象模型来处理数字签名。通过数字签名对象模型来将自定义信息添加到完全信任表单中的签名块。</span><span class="sxs-lookup"><span data-stu-id="7a976-p103">Take advantage of an object model for working with digital signatures. Add custom information to the signature block in fully trusted forms through the digital signature object model.</span></span> 
    
## <a name="overview-of-the-digital-signatures-object-model"></a><span data-ttu-id="7a976-118">数字签名对象模型概述</span><span class="sxs-lookup"><span data-stu-id="7a976-118">Overview of the Digital Signatures Object Model</span></span>

### <a name="events"></a><span data-ttu-id="7a976-119">活动</span><span class="sxs-lookup"><span data-stu-id="7a976-119">Events</span></span>

<span data-ttu-id="7a976-120">数字签名对象模型提供以下事件。</span><span class="sxs-lookup"><span data-stu-id="7a976-120">The object model for digital signatures provides the following event.</span></span>
  
|<span data-ttu-id="7a976-121">**名称**</span><span class="sxs-lookup"><span data-stu-id="7a976-121">**Name**</span></span>|<span data-ttu-id="7a976-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="7a976-122">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="7a976-123">OnSign</span><span class="sxs-lookup"><span data-stu-id="7a976-123">OnSign</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSign.aspx) <br/> |<span data-ttu-id="7a976-124">在可签名数据集被选定用于签名之后发生。</span><span class="sxs-lookup"><span data-stu-id="7a976-124">Occurs after a set of signable data has been selected to sign.</span></span>  <br/> <span data-ttu-id="7a976-p104">可以使用此事件处理数字签名中存储的数据。例如，可以添加受信任时间戳服务器中的数据，也可以添加事务的服务器端副署。此外，如果当前用户不是特定组的成员，还可以使用此事件阻止签名。</span><span class="sxs-lookup"><span data-stu-id="7a976-p104">You can use this event to manipulate the data stored within the digital signature. For example, you can add data from a trusted timestamp server, or add a server-side countersignature of the transaction. You can also use this event to block signing if the current user is not a member of a particular group.</span></span>  <br/> |
   
<span data-ttu-id="7a976-128">**OnSign** 事件返回对 [SignEventObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignEventObject.aspx) 对象的引用，它提供以下属性。</span><span class="sxs-lookup"><span data-stu-id="7a976-128">The **OnSign** event returns a reference to the [SignEventObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignEventObject.aspx) object, which provides the following properties.</span></span> 
  
|<span data-ttu-id="7a976-129">**名称**</span><span class="sxs-lookup"><span data-stu-id="7a976-129">**Name**</span></span>|<span data-ttu-id="7a976-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="7a976-130">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="7a976-131">ReturnStatus</span><span class="sxs-lookup"><span data-stu-id="7a976-131">ReturnStatus</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SignEvent.ReturnStatus.aspx) <br/> |<span data-ttu-id="7a976-132">获取或设置一个 **Boolean** 值，指示 **OnSign** 事件的返回状态。</span><span class="sxs-lookup"><span data-stu-id="7a976-132">Gets or sets a **Boolean** value indicating the return status of the **OnSign** event.</span></span>  <br/> |
|[<span data-ttu-id="7a976-133">SignedDataBlock</span><span class="sxs-lookup"><span data-stu-id="7a976-133">SignedDataBlock</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SignEvent.SignedDataBlock.aspx) <br/> |<span data-ttu-id="7a976-134">获取触发了 **OnSign** 事件的签名数据块。</span><span class="sxs-lookup"><span data-stu-id="7a976-134">Gets the signed data block that triggered the **OnSign** event.</span></span>  <br/> |
|[<span data-ttu-id="7a976-135">XDocument</span><span class="sxs-lookup"><span data-stu-id="7a976-135">XDocument</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignEvent.XDocument.aspx) <br/> |<span data-ttu-id="7a976-136">获取对与 **OnSign** 事件关联的 **XDocument** 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="7a976-136">Gets a reference to the **XDocument** object associated with the **OnSign** event.</span></span>  <br/> |
   
### <a name="collections-and-objects"></a><span data-ttu-id="7a976-137">集合和对象</span><span class="sxs-lookup"><span data-stu-id="7a976-137">Collections and Objects</span></span>

<span data-ttu-id="7a976-138">数字签名对象模型提供下列集合。</span><span class="sxs-lookup"><span data-stu-id="7a976-138">The object model for digital signatures provides the following collections.</span></span>
  
|<span data-ttu-id="7a976-139">**名称**</span><span class="sxs-lookup"><span data-stu-id="7a976-139">**Name**</span></span>|<span data-ttu-id="7a976-140">**说明**</span><span class="sxs-lookup"><span data-stu-id="7a976-140">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="7a976-141">SignedDataBlocksCollection</span><span class="sxs-lookup"><span data-stu-id="7a976-141">SignedDataBlocksCollection</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignedDataBlocksCollection.aspx) <br/> |<span data-ttu-id="7a976-142">表单模板中 [SignedDataBlockObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignedDataBlockObject.aspx) 对象的集合，如表单定义文件 (.xsf) 中所定义。</span><span class="sxs-lookup"><span data-stu-id="7a976-142">The collection of the [SignedDataBlockObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignedDataBlockObject.aspx) objects in the form template as defined in the form definition file (.xsf).</span></span>  <br/> <span data-ttu-id="7a976-p105">**SignedDataBlocksCollection** 集合实现可用于访问与表单相关联的 **SignedDataBlockObjects** 对象的属性。通过 **XDocument** 对象的 [SignedDataBlocks](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.SignedDataBlocks.aspx) 属性可以访问 [SignedDataBlocks](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) 集合。  </span><span class="sxs-lookup"><span data-stu-id="7a976-p105">The **SignedDataBlocksCollection** collection implements properties that can be used to access the **SignedDataBlockObjects** objects associated with a form. The **SignedDataBlocks** collection is accessible through the [SignedDataBlocks](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.SignedDataBlocks.aspx) property of the [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) object.  </span></span><br/> |
|[<span data-ttu-id="7a976-145">SignaturesCollection</span><span class="sxs-lookup"><span data-stu-id="7a976-145">SignaturesCollection</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignaturesCollection.aspx) <br/> |<span data-ttu-id="7a976-146">包含表单中每个 [SignedDataBlockObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignatureObject.aspx) 的 **SignatureObject** 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="7a976-146">Contains a collection of [SignatureObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignatureObject.aspx) objects for each **SignedDataBlockObject** in the form.</span></span>  <br/> <span data-ttu-id="7a976-p106">**SignaturesCollection** 集合实现一些属性和一个方法，可用于访问表单的关联 **SignatureObject** 对象以及创建签名。通过 **SignedDataBlockObject** 对象可访问它。  </span><span class="sxs-lookup"><span data-stu-id="7a976-p106">The **SignaturesCollection** collection implements properties and a method that can be used to access a form's associated **SignatureObject** objects and to create a signature. It is accessible through the **SignedDataBlockObject** object.  </span></span><br/> <span data-ttu-id="7a976-p107">在使用 [SignaturesCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Signatures.Create.aspx) 集合的 **Create** 方法时，请记住，在 [SignatureObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Signature.Sign.aspx) 对象上调用 **Sign** 方法之前，不会写入签名。只能通过完全信任的表单模板的 **OnSign** 事件处理程序来调用这些方法。  </span><span class="sxs-lookup"><span data-stu-id="7a976-p107">When you use the [Create](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Signatures.Create.aspx) method of the **SignaturesCollection** collection, keep in mind that the signature is not written until the [Sign](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Signature.Sign.aspx) method is called on the **SignatureObject** object. These methods can be called only from the **OnSign** event handler of a fully trusted form template.  </span></span><br/> |
   
<span data-ttu-id="7a976-151">数字签名对象模型提供以下对象。</span><span class="sxs-lookup"><span data-stu-id="7a976-151">The object model for digital signatures provides the following objects.</span></span>
  
|<span data-ttu-id="7a976-152">**名称**</span><span class="sxs-lookup"><span data-stu-id="7a976-152">**Name**</span></span>|<span data-ttu-id="7a976-153">**说明**</span><span class="sxs-lookup"><span data-stu-id="7a976-153">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="7a976-154">SignedDataBlockObject</span><span class="sxs-lookup"><span data-stu-id="7a976-154">SignedDataBlockObject</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignedDataBlockObject.aspx) <br/> |<span data-ttu-id="7a976-p108">表示表单中的一组可签名数据。 **SignedDataBlock** 对象提供很多属性和一个方法，可用于以编程方式与一组可签名数据进行交互。  </span><span class="sxs-lookup"><span data-stu-id="7a976-p108">Represents a set of signable data in a form. The **SignedDataBlock** object provides a number of properties and one method that can be used to programmatically interact with a set of signable data.  </span></span><br/> |
|[<span data-ttu-id="7a976-157">SignatureObject</span><span class="sxs-lookup"><span data-stu-id="7a976-157">SignatureObject</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignatureObject.aspx) <br/> |<span data-ttu-id="7a976-p109">表示已添加到表单或表单中的一组可签名数据的数字签名。 **SignatureObject** 集合实现可用于检索有关数字签名的信息的属性，以及实现用于写 XML 数字签名块并计算其加密哈希值的 [Sign](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Signature.Sign.aspx) 方法。  </span><span class="sxs-lookup"><span data-stu-id="7a976-p109">Represents a digital signature that has been added to a form or set of signable data in a form. The **SignatureObject** collection implements properties that can be used to retrieve information about the digital signature, and the [Sign](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Signature.Sign.aspx) method for writing the XML digital signature block and computing its cryptographic hash value.  </span></span><br/> |
|[<span data-ttu-id="7a976-160">CertificateObject</span><span class="sxs-lookup"><span data-stu-id="7a976-160">CertificateObject</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.CertificateObject.aspx) <br/> |<span data-ttu-id="7a976-161">代表用来创建签名的 X.509 数字证书。</span><span class="sxs-lookup"><span data-stu-id="7a976-161">Represents the X.509 digital certificate that has been used to create the signature.</span></span>  <br/> |
   
## <a name="working-with-digital-signatures-programmatically"></a><span data-ttu-id="7a976-162">以编程方式处理数字签名</span><span class="sxs-lookup"><span data-stu-id="7a976-162">Working with Digital Signatures Programmatically</span></span>

<span data-ttu-id="7a976-p110">InfoPath 2003 兼容对象模型提供了以编程方式与数字签名进行交互的成员。特别是，根据以下时间线，在提交签名块之前，完全信任的表单可以向其添加自定义信息：</span><span class="sxs-lookup"><span data-stu-id="7a976-p110">The InfoPath 2003-compatible object model provides members for interacting with digital signatures programmatically. In particular, fully-trusted forms can add custom information to the signature block before it is committed, according to the following timeline:</span></span>
  
1. <span data-ttu-id="7a976-165">用户选择向表单添加数字签名。</span><span class="sxs-lookup"><span data-stu-id="7a976-165">User chooses to add a digital signature to a form.</span></span>
    
2. <span data-ttu-id="7a976-166">随即会显示“**数字签名向导**”的第一个窗格。</span><span class="sxs-lookup"><span data-stu-id="7a976-166">The first panel of the **Digital Signature Wizard** is displayed.</span></span> 
    
3. <span data-ttu-id="7a976-167">由 **SignedDataBlockObject** 对象代表的选定数据的 **OnSign** 事件被触发，并且执行 **SignedDataBlockObject** 的 **Sign** 方法，以及 **SignaturesCollection** 集合的 **Create** 方法。</span><span class="sxs-lookup"><span data-stu-id="7a976-167">The **OnSign** event for the selected data represented by the **SignedDataBlockObject** object is raised, and the **Sign** method of **SignedDataBlockObject** and the **Create** method of the **SignaturesCollection** collection are executed.</span></span> 
    
4. <span data-ttu-id="7a976-168">执行任何可选的自定义操作。</span><span class="sxs-lookup"><span data-stu-id="7a976-168">Any optional custom actions are executed.</span></span>
    
5. <span data-ttu-id="7a976-169">执行 **SignatureObject** 的 **Sign** 方法。</span><span class="sxs-lookup"><span data-stu-id="7a976-169">The **Sign** method of the **SignatureObject** is executed.</span></span> 
    
6. <span data-ttu-id="7a976-170">向导的第二和第三个窗格将会显示，供用户选择签名时所用的证书和输入注释。</span><span class="sxs-lookup"><span data-stu-id="7a976-170">Second and third panes of the wizard are displayed for selecting a certificate to sign with and to enter comments.</span></span>
    
7. <span data-ttu-id="7a976-171">随即显示不可否认信息（稍后可在“**验证数字签名**”对话框中查看）。</span><span class="sxs-lookup"><span data-stu-id="7a976-171">The non-repudiation information is displayed (which can be viewed later with the **Verify Digital Signature** dialog box).</span></span> 
    
8. <span data-ttu-id="7a976-172">点击“**签名**”按钮后，签名将添加到表单的签名集合中。</span><span class="sxs-lookup"><span data-stu-id="7a976-172">When the **Sign** button is clicked, the signature is added to collection of signatures for the form.</span></span> 
    
<span data-ttu-id="7a976-173">下面的示例调用“**签名**”对话框并向签名副署一个从受信任的时间戳服务获取的时间戳值。</span><span class="sxs-lookup"><span data-stu-id="7a976-173">The following example invokes the **Sign** dialog box and countersigns the signature with a timestamp value retrieved from a trusted timestamp service.</span></span> 
  
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


