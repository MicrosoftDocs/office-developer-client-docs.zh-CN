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
ms.openlocfilehash: 1277998edf4feb94da40d82372fd4d96fedf2d54
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19774038"
---
# <a name="work-with-digital-signatures"></a><span data-ttu-id="e1039-104">使用数字签名</span><span class="sxs-lookup"><span data-stu-id="e1039-104">Work with Digital Signatures?</span></span>

<span data-ttu-id="e1039-105">[Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间的对象模型提供了以编程方式使用数字签名的功能。</span><span class="sxs-lookup"><span data-stu-id="e1039-105">The object model of the [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) namespace provides features for working with digital signatures programmatically.</span></span> 
  
## <a name="digital-signature-features"></a><span data-ttu-id="e1039-106">数字签名功能</span><span class="sxs-lookup"><span data-stu-id="e1039-106">Digital Signature Features</span></span>

<span data-ttu-id="e1039-107">通过 InfoPath 提供的数字签名功能，您可以：</span><span class="sxs-lookup"><span data-stu-id="e1039-107">The digital signatures features provided by InfoPath enable you to:</span></span> 
  
- <span data-ttu-id="e1039-108">为整个表单启用签名，或者为表单中可单独签名的特定数据集启用签名。</span><span class="sxs-lookup"><span data-stu-id="e1039-108">Enable signatures for the entire form, or for specific sets of data in the form that can be signed separately.</span></span>
    
- <span data-ttu-id="e1039-p101">对于可签名的每一个数据集，指定允许单个还是多个签名，并指定它们之间的关系。例如，可以指定它们是否是并行联署，以及每个新的签名是否都副署所有更早的签名。</span><span class="sxs-lookup"><span data-stu-id="e1039-p101">Specify, for each set of data that can be signed, whether a single signature or multiple signatures are allowed and what their relationship will be. For example, you can specify whether they are parallel co-signatures or whether each new signature countersigns all the earlier signatures.</span></span>
    
- <span data-ttu-id="e1039-111">指定当表单用户签署表单时将显示给表单用户的消息。</span><span class="sxs-lookup"><span data-stu-id="e1039-111">Specify a message to be shown to form users as they sign the form.</span></span>
    
- <span data-ttu-id="e1039-112">在文档中插入和查看签名。</span><span class="sxs-lookup"><span data-stu-id="e1039-112">Insert and see a signature in the document.</span></span> 
    
- <span data-ttu-id="e1039-113">查看已添加到每个签名来提高安全性的可验证的不可否认性信息。</span><span class="sxs-lookup"><span data-stu-id="e1039-113">View verifiable non-repudiation information that has been added to each signature for increased security.</span></span> <span data-ttu-id="e1039-114">此额外信息（其中包含表单的视图，因为它呈现给每个签名者）是签名的一部分，未使签名无效的情况下不可删除。</span><span class="sxs-lookup"><span data-stu-id="e1039-114">View verifiable non-repudiation information that has been added to each signature for increased security. This additional information, which includes a view of the form as it was presented to each signer, is part of the signature and cannot be removed without invalidating the signature. At any time, you can recall this data by clicking on the signature in the form to display the Verify Digital Signature dialog box.</span></span> <span data-ttu-id="e1039-115">可以通过单击表单中的签名以显示****“验证数字签名”对话框来随时撤回此数据。</span><span class="sxs-lookup"><span data-stu-id="e1039-115">At any time, you can recall this data by clicking on the signature in the form to display the **Verify Digital Signature** dialog box.</span></span> 
    
- <span data-ttu-id="e1039-p103">利用对象模型来处理数字签名。通过数字签名对象模型来将自定义信息添加到完全信任表单中的签名块。</span><span class="sxs-lookup"><span data-stu-id="e1039-p103">Take advantage of an object model for working with digital signatures. Add custom information to the signature block in fully trusted forms through the digital signature object model.</span></span> 
    
## <a name="overview-of-the-digital-signatures-object-model"></a><span data-ttu-id="e1039-118">数字签名对象模型概述</span><span class="sxs-lookup"><span data-stu-id="e1039-118">Overview of the Digital Signatures Object Model</span></span>

### <a name="the-sign-event"></a><span data-ttu-id="e1039-119">Sign 事件</span><span class="sxs-lookup"><span data-stu-id="e1039-119">The Sign Event</span></span>

<span data-ttu-id="e1039-120">数字签名对象模型提供以下事件。</span><span class="sxs-lookup"><span data-stu-id="e1039-120">The object model for digital signatures provides the following event.</span></span>
  
|<span data-ttu-id="e1039-121">**名称**</span><span class="sxs-lookup"><span data-stu-id="e1039-121">**Name**</span></span>|<span data-ttu-id="e1039-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="e1039-122">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e1039-123">Sign</span><span class="sxs-lookup"><span data-stu-id="e1039-123">Sign</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Sign.aspx) <br/> |<span data-ttu-id="e1039-124">在选择要签名的数据组之后发生。</span><span class="sxs-lookup"><span data-stu-id="e1039-124">Occurs after a set of data has been selected to sign.</span></span>  <br/> <span data-ttu-id="e1039-p104">可以使用此事件处理数字签名中存储的数据。例如，可以添加受信任时间戳服务器中的数据，也可以添加事务的服务器端副署。此外，如果当前用户不是特定组的成员，还可以使用此事件阻止签名。</span><span class="sxs-lookup"><span data-stu-id="e1039-p104">You can use this event to manipulate the data stored within the digital signature. For example, you can add data from a trusted timestamp server, or add a server-side countersignature of the transaction. You can also use this event to block signing if the current user is not a member of a particular group.</span></span>  <br/> |
   
### <a name="the-signeventargs-object"></a><span data-ttu-id="e1039-128">SignEventArgs 对象</span><span class="sxs-lookup"><span data-stu-id="e1039-128">The SignEventArgs Object</span></span>

<span data-ttu-id="e1039-129">[Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Sign.aspx) 事件的事件处理程序可以处理 [SignEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignEventArgs.aspx) 事件对象，该对象提供下列属性。</span><span class="sxs-lookup"><span data-stu-id="e1039-129">An event handler for the [Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Sign.aspx) event can work with the [SignEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignEventArgs.aspx) event object, which provides the following properties.</span></span> 
  
|<span data-ttu-id="e1039-130">**名称**</span><span class="sxs-lookup"><span data-stu-id="e1039-130">**Name**</span></span>|<span data-ttu-id="e1039-131">**说明**</span><span class="sxs-lookup"><span data-stu-id="e1039-131">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e1039-132">SignedDataBlock</span><span class="sxs-lookup"><span data-stu-id="e1039-132">SignedDataBlock</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignEventArgs.SignedDataBlock.aspx) <br/> |<span data-ttu-id="e1039-133">获取引发 [Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Sign.aspx) 事件的数据组。</span><span class="sxs-lookup"><span data-stu-id="e1039-133">Gets the set of data that raised the [Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Sign.aspx) event.</span></span>  <br/> |
|[<span data-ttu-id="e1039-134">SignatureWizard</span><span class="sxs-lookup"><span data-stu-id="e1039-134">SignatureWizard</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignEventArgs.SignatureWizard.aspx) <br/> |<span data-ttu-id="e1039-135">获取或设置是否显示****“数字签名”对话框。</span><span class="sxs-lookup"><span data-stu-id="e1039-135">Gets or sets whether to display the **Digital Signatures** dialog box.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="e1039-p105">在随 InfoPath 2003 一起提供的 [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 托管代码对象模型中， [OnSign](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignEvent.aspx) 事件的 [SignEvent](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2.OnSign.aspx) 事件对象提供了一个 **XDocument** 属性，用来访问与该事件关联的表单的 **XDocument** 对象。这对于通过 InfoPath Forms Services 或 InfoPath 使用 [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 对象模型创建的表单模板并不是必需的，这是因为可以使用 [this](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) (C#) 或 **Me** (Visual Basic) 关键字在表单代码中访问 **XmlForm** 类的对象模型成员。例如，若要访问 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Signed.aspx) 类的 [Signed](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 属性以确定某个表单是否经过签名，您可以键入  `this.Signed` 或  `Me.Signed.`。</span><span class="sxs-lookup"><span data-stu-id="e1039-p105">In the [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) managed code object model that shipped with InfoPath 2003, the [SignEvent](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignEvent.aspx) event object for the [OnSign](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2.OnSign.aspx) event provides an **XDocument** property for accessing the **XDocument** object of the form associated with the event. This is not necessary with form templates created with InfoPath Forms Services or InfoPath using the [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) object model because the object model members of the [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) class can be accessed in form code using the **this** (C#) or **Me** (Visual Basic) keyword. For example, to access the [Signed](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Signed.aspx) property of the [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) class to determine if a form is signed, you can type either  `this.Signed` or  `Me.Signed.`</span></span>
  
### <a name="collections-and-objects"></a><span data-ttu-id="e1039-139">集合和对象</span><span class="sxs-lookup"><span data-stu-id="e1039-139">Collections and Objects</span></span>

<span data-ttu-id="e1039-140">数字签名对象模型提供下列集合。</span><span class="sxs-lookup"><span data-stu-id="e1039-140">The object model for digital signatures provides the following collections.</span></span>
  
|<span data-ttu-id="e1039-141">**名称**</span><span class="sxs-lookup"><span data-stu-id="e1039-141">**Name**</span></span>|<span data-ttu-id="e1039-142">**说明**</span><span class="sxs-lookup"><span data-stu-id="e1039-142">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e1039-143">SignedDataBlockCollection</span><span class="sxs-lookup"><span data-stu-id="e1039-143">SignedDataBlockCollection</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlockCollection.aspx) <br/> |<span data-ttu-id="e1039-144">设计时在 InfoPath 设计模式下定义的表单模板中的 [SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="e1039-144">The collection of the [SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) objects in the form template as defined at design time in InfoPath design mode.</span></span>  <br/> <span data-ttu-id="e1039-p106">[SignedDataBlockCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlockCollection.aspx) 集合实现了可用于访问与表单关联的 [SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) 对象的属性。可以通过 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlockCollection.aspx) 类的 [SignedDataBlocks](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.SignedDataBlocks.aspx) 属性来访问与表单关联的 [SignedDataBlockCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 对象。  </span><span class="sxs-lookup"><span data-stu-id="e1039-p106">The [SignedDataBlockCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlockCollection.aspx) collection implements properties that can be used to access the [SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) objects associated with a form. The [SignedDataBlockCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlockCollection.aspx) object associated with a form is accessible through the [SignedDataBlocks](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.SignedDataBlocks.aspx) property of the [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) class.  </span></span><br/> |
|[<span data-ttu-id="e1039-147">SignatureCollection</span><span class="sxs-lookup"><span data-stu-id="e1039-147">SignatureCollection</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.aspx) <br/> |<span data-ttu-id="e1039-148">对于表单中的每个 [SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.aspx) 对象，都包含 [Signature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="e1039-148">Contains a collection of [Signature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.aspx) objects for each [SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) object in the form.</span></span>  <br/> <span data-ttu-id="e1039-p107">[SignatureCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.aspx) 类实现一些属性和一个方法，可用于访问与表单关联的 [Signature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.aspx) 对象以及用于创建签名。可以使用 [Signatures](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.aspx) 属性访问与 [SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) 关联的 [SignatureCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.Signatures.aspx) 对象。  </span><span class="sxs-lookup"><span data-stu-id="e1039-p107">The [SignatureCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.aspx) class implements properties and a method that can be used to access a form's associated [Signature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.aspx) objects and to create a signature. The [SignatureCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.aspx) object associated with a [SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) is accessible using the [Signatures](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.Signatures.aspx) property.  </span></span><br/> <span data-ttu-id="e1039-p108">在使用 [SignatureCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.CreateSignature.aspx) 类的 [CreateSignature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.aspx) 方法时，请记住，在对 [Signature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.Sign.aspx) 对象调用 [Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.aspx) 方法之前不会写入签名。只能通过完全信任的表单模板的 **Sign** 事件处理程序来调用这些方法。  </span><span class="sxs-lookup"><span data-stu-id="e1039-p108">When you use the [CreateSignature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.CreateSignature.aspx) method of the [SignatureCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.aspx) class, keep in mind that the signature is not written until the [Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.Sign.aspx) method is called on the [Signature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.aspx) object. These methods can be called only from the **Sign** event handler of a fully trusted form template.  </span></span><br/> |
   
<span data-ttu-id="e1039-153">数字签名对象模型提供下列对象。</span><span class="sxs-lookup"><span data-stu-id="e1039-153">The object model for digital signatures provides the following objects.</span></span>
  
|<span data-ttu-id="e1039-154">**名称**</span><span class="sxs-lookup"><span data-stu-id="e1039-154">**Name**</span></span>|<span data-ttu-id="e1039-155">**说明**</span><span class="sxs-lookup"><span data-stu-id="e1039-155">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e1039-156">SignedDataBlock</span><span class="sxs-lookup"><span data-stu-id="e1039-156">SignedDataBlock</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) <br/> |<span data-ttu-id="e1039-p109">表示表单中的一组可签名数据。[SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) 对象提供很多属性和一个方法，可用于以编程方式与一组可签名数据进行交互。</span><span class="sxs-lookup"><span data-stu-id="e1039-p109">Represents a set of signable data in a form. The [SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) object provides a number of properties and one method that can be used to programmatically interact with a set of signable data.  </span></span><br/> |
|[<span data-ttu-id="e1039-159">Signature</span><span class="sxs-lookup"><span data-stu-id="e1039-159">Signature</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.aspx) <br/> |<span data-ttu-id="e1039-p110">表示已添加到表单或表单中的一组可签名数据的数字签名。[Signature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.aspx) 对象实现可用于检索有关数字签名的信息的属性，以及用于编写 XML 数字签名块并计算其加密哈希值的 [Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.Sign.aspx) 方法。</span><span class="sxs-lookup"><span data-stu-id="e1039-p110">Represents a digital signature that has been added to a form or set of signable data in a form. The [Signature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.aspx) object implements properties that can be used to retrieve information about the digital signature, and the [Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.Sign.aspx) method for writing the XML digital signature block and computing its cryptographic hash value.  </span></span><br/> |
|[<span data-ttu-id="e1039-162">Certificate</span><span class="sxs-lookup"><span data-stu-id="e1039-162">Certificate</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Certificate.aspx) <br/> |<span data-ttu-id="e1039-163">代表用来创建签名的 X.509 数字证书。</span><span class="sxs-lookup"><span data-stu-id="e1039-163">Represents the X.509 digital certificate that has been used to create the signature.</span></span>  <br/> |
   
## <a name="working-with-digital-signatures-programmatically"></a><span data-ttu-id="e1039-164">以编程方式处理数字签名</span><span class="sxs-lookup"><span data-stu-id="e1039-164">Working with Digital Signatures Programmatically</span></span>

<span data-ttu-id="e1039-p111">[Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间的对象模型提供了以编程方式与数字签名进行交互的成员。特别是，根据以下时间线，在提交签名块之前，完全信任的表单可以向其添加自定义信息：</span><span class="sxs-lookup"><span data-stu-id="e1039-p111">The object model of the [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) namespace provides members for interacting with digital signatures programmatically. In particular, fully-trusted forms can add custom information to the signature block before it is committed, according to the following timeline:</span></span> 
  
1. <span data-ttu-id="e1039-167">用户选择向表单添加数字签名。</span><span class="sxs-lookup"><span data-stu-id="e1039-167">User chooses to add a digital signature to a form.</span></span>
    
2. <span data-ttu-id="e1039-168">显示“数字签名”**** 对话框，用户单击“添加”****，然后选择要签署的数据。</span><span class="sxs-lookup"><span data-stu-id="e1039-168">The **Digital Signatures **dialog box is displayed, the user clicks **Add**, and then selects the data to sign.</span></span>
    
3. <span data-ttu-id="e1039-169">引发由 [SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Sign.aspx) 对象代表的选定数据的 [Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) 事件，并执行 [SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.Sign.aspx) 对象的 [Sign()](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) 方法以及 [SignatureCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.CreateSignature.aspx) 集合的 [CreateSignature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.aspx) 方法。</span><span class="sxs-lookup"><span data-stu-id="e1039-169">The [Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Sign.aspx) event for the selected data represented by the [SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) object is raised, and the [Sign()](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.Sign.aspx) method of [SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) object and the [CreateSignature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.CreateSignature.aspx) method of the [SignatureCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignatureCollection.aspx) collection are executed.</span></span> 
    
4. <span data-ttu-id="e1039-170">执行任何可选的自定义操作。</span><span class="sxs-lookup"><span data-stu-id="e1039-170">Any optional custom actions are executed.</span></span>
    
5. <span data-ttu-id="e1039-171">执行 [Signature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.Sign.aspx) 对象的 [Sign()](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.aspx) 方法。</span><span class="sxs-lookup"><span data-stu-id="e1039-171">The [Sign()](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.Sign.aspx) method of the [Signature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.aspx) object is executed.</span></span> 
    
6. <span data-ttu-id="e1039-172">显示“签名”**** 对话框，用来键入一个名称（或选择一个签名图像），选择签名时使用的证书以及输入注释。</span><span class="sxs-lookup"><span data-stu-id="e1039-172">The **Sign** dialog box is displayed for typing a name (or selecting a signature image), selecting a certificate to sign with, and to enter comments.</span></span> 
    
7. <span data-ttu-id="e1039-173">单击“签名”**** 按钮时，签名将添加到表单的签名集合中，并且将捕获认可信息并与签名一起保存（以后可通过单击“数字签名”**** 对话框中的“查看签名的表单”****，然后单击“查看收集的附加签名信息”**** 来查看）。</span><span class="sxs-lookup"><span data-stu-id="e1039-173">When the **Sign** button is clicked, the signature is added to the collection of signatures for the form and the non-repudiation information is captured and saved with the signature (which can be viewed later by clicking **View Signed Form** on the **Digital Signatures** dialog box, and then clicking **See the additional signing information that was collected**).</span></span>
    
<span data-ttu-id="e1039-174">下面的示例在用户签署所选数据时调用 [Sign()](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.Sign.aspx) 方法，并利用从受信任的时间戳服务中检索的时间戳值来副署签名。</span><span class="sxs-lookup"><span data-stu-id="e1039-174">The following example invokes the [Sign()](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.Sign.aspx) method when the user signs the selected data and countersigns the signature with a timestamp value retrieved from a trusted timestamp service.</span></span> 
  
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


