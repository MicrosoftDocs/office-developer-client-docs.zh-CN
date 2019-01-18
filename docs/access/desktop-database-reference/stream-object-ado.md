---
title: Stream 对象 (ADO)
TOCTitle: Stream object (ADO)
ms:assetid: d49b1514-e0b4-0aca-d5c2-8266f3f4fe65
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250065(v=office.15)
ms:contentKeyID: 48547945
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 1f6d7e8f64f6b14ea699006fc0461cdf0ded2a06
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28704425"
---
# <a name="stream-object-ado"></a><span data-ttu-id="ffad7-102">Stream 对象 (ADO)</span><span class="sxs-lookup"><span data-stu-id="ffad7-102">Stream object (ADO)</span></span>


<span data-ttu-id="ffad7-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="ffad7-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ffad7-104">代表二进制数据流或文本流。</span><span class="sxs-lookup"><span data-stu-id="ffad7-104">Represents a stream of binary data or text.</span></span>

## <a name="remarks"></a><span data-ttu-id="ffad7-105">说明</span><span class="sxs-lookup"><span data-stu-id="ffad7-105">Remarks</span></span>

<span data-ttu-id="ffad7-106">树状层次结构例如文件系统或电子邮件系统，[记录](record-object-ado.md)可能包含的文件或电子邮件的内容与之关联的二进制文件的默认二进制流。</span><span class="sxs-lookup"><span data-stu-id="ffad7-106">In tree-structured hierarchies such as a file system or an email system, a [Record](record-object-ado.md) may have a default binary stream of bits associated with it that contains the contents of the file or the email.</span></span> <span data-ttu-id="ffad7-107">**Stream** 对象可以用来处理包含这些数据流的字段或记录。</span><span class="sxs-lookup"><span data-stu-id="ffad7-107">A **Stream** object can be used to manipulate fields or records containing these streams of data.</span></span> <span data-ttu-id="ffad7-108">可以通过以下方式获得 **Stream** 对象：</span><span class="sxs-lookup"><span data-stu-id="ffad7-108">A **Stream** object can be obtained in these ways:</span></span>

  - <span data-ttu-id="ffad7-p102">从指向包含二进制数据或文本数据的对象（通常为文件）的 URL 获得。该对象可以是简单文档、表示结构化文档的 **Record** 对象或文件夹。</span><span class="sxs-lookup"><span data-stu-id="ffad7-p102">From a URL pointing to an object (typically a file) containing binary or text data. This object can be a simple document, a **Record** object representing a structured document, or a folder.</span></span>

  - <span data-ttu-id="ffad7-p103">通过打开与 **Record** 对象关联的默认 **Stream** 对象获得。打开 **Record** 对象时，您可以获得与 **Record** 对象关联的默认流，以免除仅为打开默认流所需的往返行程。</span><span class="sxs-lookup"><span data-stu-id="ffad7-p103">By opening the default **Stream** object associated with a **Record** object. You can obtain the default stream associated with a **Record** object when the **Record** is opened, to eliminate a round-trip just to open the stream.</span></span>

  - <span data-ttu-id="ffad7-p104">通过实例化 **Stream** 对象获得。使用这些 **Stream** 对象可存储用于应用程序的数据。与那些与 URL 关联的 **Stream** 或 **Record** 的默认 **Stream** 不同，实例化的 **Stream** 默认情况下与基础源没有任何关联。</span><span class="sxs-lookup"><span data-stu-id="ffad7-p104">By instantiating a **Stream** object. These **Stream** objects can be used to store data for the purposes of your application. Unlike a **Stream** associated with a URL, or the default **Stream** of a **Record**, an instantiated **Stream** has no association with an underlying source by default.</span></span>

<span data-ttu-id="ffad7-116">使用 **Stream** 对象的方法和属性，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ffad7-116">With the methods and properties of a **Stream** object, you can do the following:</span></span>

  - <span data-ttu-id="ffad7-117">使用 **Open** 方法通过 **Record** 或 URL 打开 [Stream](open-method-ado-stream.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="ffad7-117">Open a **Stream** object from a **Record** or URL with the [Open](open-method-ado-stream.md) method.</span></span>

  - <span data-ttu-id="ffad7-118">使用 **Close** 方法关闭 [Stream](close-method-ado.md) 。</span><span class="sxs-lookup"><span data-stu-id="ffad7-118">Close a **Stream** with the [Close](close-method-ado.md) method.</span></span>

  - <span data-ttu-id="ffad7-119">使用 **Write** 和 [WriteText](write-method-ado.md) 方法向 [Stream](writetext-method-ado.md) 输入字节或文本。</span><span class="sxs-lookup"><span data-stu-id="ffad7-119">Input bytes or text to a **Stream** with the [Write](write-method-ado.md) and [WriteText](writetext-method-ado.md) methods.</span></span>

  - <span data-ttu-id="ffad7-120">使用 **Read** 和 [ReadText](read-method-ado.md) 方法从 [Stream](readtext-method-ado.md) 读取字节。</span><span class="sxs-lookup"><span data-stu-id="ffad7-120">Read bytes from the **Stream** with the [Read](read-method-ado.md) and [ReadText](readtext-method-ado.md) methods.</span></span>

  - <span data-ttu-id="ffad7-121">使用 **Flush** 方法将仍在 ADO 缓冲区中的任何 [Stream](flush-method-ado.md) 数据写入基础对象。</span><span class="sxs-lookup"><span data-stu-id="ffad7-121">Write any **Stream** data still in the ADO buffer to the underlying object with the [Flush](flush-method-ado.md) method.</span></span>

  - <span data-ttu-id="ffad7-122">使用 **CopyTo** 方法将一个 **Stream** 中的内容复制到其他 [Stream](copyto-method-ado.md) 中。</span><span class="sxs-lookup"><span data-stu-id="ffad7-122">Copy the contents of a **Stream** to another **Stream** with the [CopyTo](copyto-method-ado.md) method.</span></span>

  - <span data-ttu-id="ffad7-123">使用 [SkipLine](skipline-method-ado.md) 方法和 [LineSeparator](lineseparator-property-ado.md) 属性控制从源文件读取行的方式。</span><span class="sxs-lookup"><span data-stu-id="ffad7-123">Control how lines are read from the source file with the [SkipLine](skipline-method-ado.md) method and the [LineSeparator](lineseparator-property-ado.md) property.</span></span>

  - <span data-ttu-id="ffad7-124">使用 [EOS](eos-property-ado.md) 属性和 [SetEOS](seteos-method-ado.md) 方法确定流的末尾位置。</span><span class="sxs-lookup"><span data-stu-id="ffad7-124">Determine the end of stream position with the [EOS](eos-property-ado.md) property and [SetEOS](seteos-method-ado.md) method.</span></span>

  - <span data-ttu-id="ffad7-125">使用 [SaveToFile](savetofile-method-ado.md) 和 [LoadFromFile](loadfromfile-method-ado.md) 方法保存和还原文件中的数据。</span><span class="sxs-lookup"><span data-stu-id="ffad7-125">Save and restore data in files with the [SaveToFile](savetofile-method-ado.md) and [LoadFromFile](loadfromfile-method-ado.md) methods.</span></span>

  - <span data-ttu-id="ffad7-126">使用 **Charset** 属性指定用于存储 [Stream](charset-property-ado.md) 的字符集。</span><span class="sxs-lookup"><span data-stu-id="ffad7-126">Specify the character set used for storing the **Stream** with the [Charset](charset-property-ado.md) property.</span></span>

  - <span data-ttu-id="ffad7-127">使用 **Cancel** 方法中止异步 [Stream](cancel-method-ado.md) 操作。</span><span class="sxs-lookup"><span data-stu-id="ffad7-127">Halt an asynchronous **Stream** operation with the [Cancel](cancel-method-ado.md) method.</span></span>

  - <span data-ttu-id="ffad7-128">使用 **Size** 属性确定 [Stream](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/size-property-ado-stream) 中的字节数。</span><span class="sxs-lookup"><span data-stu-id="ffad7-128">Determine the number of bytes in a **Stream** with the [Size](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/size-property-ado-stream) property.</span></span>

  - <span data-ttu-id="ffad7-129">使用 **Position** 属性控制 [Stream](position-property-ado.md) 中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="ffad7-129">Control the current position within a **Stream** with the [Position](position-property-ado.md) property.</span></span>

  - <span data-ttu-id="ffad7-130">使用 **Type** 属性确定 [Stream](type-property-ado-stream.md) 中的数据类型。</span><span class="sxs-lookup"><span data-stu-id="ffad7-130">Determine the type of data in a **Stream** with the [Type](type-property-ado-stream.md) property.</span></span>

  - <span data-ttu-id="ffad7-131">使用 **State** 属性确定 [Stream](state-property-ado.md) 的当前状态（关闭、打开和正在执行）。</span><span class="sxs-lookup"><span data-stu-id="ffad7-131">Determine the current state of the **Stream** (closed, open, or executing) with the [State](state-property-ado.md) property.</span></span>

  - <span data-ttu-id="ffad7-132">使用 **Mode** 属性指定 [Stream](mode-property-ado.md) 的访问模式。</span><span class="sxs-lookup"><span data-stu-id="ffad7-132">Specify the access mode for the **Stream** with the [Mode](mode-property-ado.md) property.</span></span>

> [!NOTE]
> <span data-ttu-id="ffad7-133">[!注释] 使用 http 方案的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。</span><span class="sxs-lookup"><span data-stu-id="ffad7-133">URLs using the http scheme will automatically invoke the [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md).</span></span> <span data-ttu-id="ffad7-134">有关详细信息，请参阅[绝对和相对 Url](absolute-and-relative-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="ffad7-134">For more information, see [Absolute and relative URLs](absolute-and-relative-urls.md).</span></span>


