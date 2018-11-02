---
title: LoadFromFile 方法 (ADO)
TOCTitle: LoadFromFile method (ADO)
ms:assetid: 33fd543f-bd24-9199-7540-2889b69221c8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249107(v=office.15)
ms:contentKeyID: 48544123
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 96bc0f55f6524a2aaa04bbe1f9b591ff2eb85bb8
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25925721"
---
# <a name="loadfromfile-method-ado"></a><span data-ttu-id="13ef5-102">LoadFromFile 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="13ef5-102">LoadFromFile method (ADO)</span></span>


<span data-ttu-id="13ef5-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="13ef5-103">**Applies to**: Access 2013, Office 2013</span></span>



<span data-ttu-id="13ef5-104">用于将现有文件的内容加载到 [Stream](stream-object-ado.md) 中。</span><span class="sxs-lookup"><span data-stu-id="13ef5-104">Loads the contents of an existing file into a [Stream](stream-object-ado.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="13ef5-105">语法</span><span class="sxs-lookup"><span data-stu-id="13ef5-105">Syntax</span></span>

<span data-ttu-id="13ef5-106">*流*。LoadFromFile*文件名*</span><span class="sxs-lookup"><span data-stu-id="13ef5-106">*Stream*.LoadFromFile *FileName*</span></span>

## <a name="parameter"></a><span data-ttu-id="13ef5-107">参数</span><span class="sxs-lookup"><span data-stu-id="13ef5-107">Parameter</span></span>

  - <span data-ttu-id="13ef5-108">*FileName*</span><span class="sxs-lookup"><span data-stu-id="13ef5-108">*FileName*</span></span>

  - <span data-ttu-id="13ef5-109">**字符串型** 值，包含要加载到 **Stream** 中的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="13ef5-109">A **String** value that contains the name of a file to be loaded into the **Stream**.</span></span> <span data-ttu-id="13ef5-110">*FileName*可以包含任何有效路径和名称采用 UNC 格式。</span><span class="sxs-lookup"><span data-stu-id="13ef5-110">*FileName* can contain any valid path and name in UNC format.</span></span> <span data-ttu-id="13ef5-111">如果指定的文件不存在，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="13ef5-111">If the specified file does not exist, a run-time error occurs.</span></span>

## <a name="remarks"></a><span data-ttu-id="13ef5-112">备注</span><span class="sxs-lookup"><span data-stu-id="13ef5-112">Remarks</span></span>

<span data-ttu-id="13ef5-p102">可以使用该方法将本地文件的内容加载到 **Stream** 对象中。通过这种方式可以将本地文件的内容上载到服务器。</span><span class="sxs-lookup"><span data-stu-id="13ef5-p102">This method may be used to load the contents of a local file into a **Stream** object. This may be used to upload the contents of a local file to a server.</span></span>

<span data-ttu-id="13ef5-p103">调用 **LoadFromFile** 之前， **Stream** 对象必须已经打开。该方法不会更改 **Stream** 对象的绑定；它将仍然绑定到由 URL 或最初用于打开 **Stream** 的 **Record** 指定的对象。</span><span class="sxs-lookup"><span data-stu-id="13ef5-p103">The **Stream** object must be already open before calling **LoadFromFile**. This method does not change the binding of the **Stream** object; it will still be bound to the object specified by the URL or **Record** with which the **Stream** was originally opened.</span></span>

<span data-ttu-id="13ef5-p104">**LoadFromFile** 使用从文件读取的数据覆盖 **Stream** 对象的当前内容。 **Stream** 中的任何现有字节都被文件内容覆盖。 [LoadFromFile](eos-property-ado.md) 创建的 **EOS** 后面的任何以前存在的字节和剩余的字节都会被截去。</span><span class="sxs-lookup"><span data-stu-id="13ef5-p104">**LoadFromFile** overwrites the current contents of the **Stream** object with data read from the file. Any existing bytes in the **Stream** are overwritten by the contents of the file. Any previously existing and remaining bytes following the [EOS](eos-property-ado.md) created by **LoadFromFile**, are truncated.</span></span>

<span data-ttu-id="13ef5-120">调用 **LoadFromFile** 之后，当前位置设置为 **Stream** 的开头（[Position](position-property-ado.md) 为 0）。</span><span class="sxs-lookup"><span data-stu-id="13ef5-120">After a call to **LoadFromFile**, the current position is set to the beginning of the **Stream** ([Position](position-property-ado.md) is 0).</span></span>

<span data-ttu-id="13ef5-121">由于可能会向流的开头添加 2 个字节以进行编码，因此流大小与加载该流的文件的大小可能并不完全匹配。</span><span class="sxs-lookup"><span data-stu-id="13ef5-121">Because 2 bytes may be added to the beginning of the stream for encoding, the size of the stream may not exactly match the size of the file from which it was loaded.</span></span>

