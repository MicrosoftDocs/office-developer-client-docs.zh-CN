---
title: ReadText 方法 (ADO)
TOCTitle: ReadText Method (ADO)
ms:assetid: 08f5bac4-dccd-696c-09a7-e1ba0cb38d79
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248826(v=office.15)
ms:contentKeyID: 48543108
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3a44a3a002d390879e5d56d9c6931a91cba40271
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465547"
---
# <a name="readtext-method-ado"></a><span data-ttu-id="6c395-102">ReadText 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="6c395-102">ReadText Method (ADO)</span></span>


<span data-ttu-id="6c395-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="6c395-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="6c395-104">可从文本 [Stream](stream-object-ado.md) 对象读取指定数量的字符。</span><span class="sxs-lookup"><span data-stu-id="6c395-104">Reads specified number of characters from a text [Stream](stream-object-ado.md) object.</span></span>

## <a name="syntax"></a><span data-ttu-id="6c395-105">语法</span><span class="sxs-lookup"><span data-stu-id="6c395-105">Syntax</span></span>

<span data-ttu-id="6c395-106">*字符串* = *流*。ReadText (*NumChars*)</span><span class="sxs-lookup"><span data-stu-id="6c395-106">*String* = *Stream*.ReadText (*NumChars*)</span></span>

## <a name="parameters"></a><span data-ttu-id="6c395-107">参数</span><span class="sxs-lookup"><span data-stu-id="6c395-107">Parameters</span></span>

  - <span data-ttu-id="6c395-108">*NumChars*</span><span class="sxs-lookup"><span data-stu-id="6c395-108">*NumChars*</span></span>

  - <span data-ttu-id="6c395-p101">可选。 **长整型** 值，指定要从文件读取的字符数或 [StreamReadEnum](streamreadenum.md) 值。默认值为 **adReadAll** 。</span><span class="sxs-lookup"><span data-stu-id="6c395-p101">Optional. A **Long** value that specifies the number of characters to read from the file, or a [StreamReadEnum](streamreadenum.md) value. The default value is **adReadAll**.</span></span>

## <a name="return-value"></a><span data-ttu-id="6c395-112">返回值</span><span class="sxs-lookup"><span data-stu-id="6c395-112">Return Value</span></span>

<span data-ttu-id="6c395-113">**ReadText** 方法从 **Stream** 对象读取指定数量的字符、一整行或整个流，并返回结果字符串。</span><span class="sxs-lookup"><span data-stu-id="6c395-113">The **ReadText** method reads a specified number of characters, an entire line, or the entire stream from a **Stream** object and returns the resulting string.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c395-114">备注</span><span class="sxs-lookup"><span data-stu-id="6c395-114">Remarks</span></span>

<span data-ttu-id="6c395-p102">如果 *NumChar* 大于流中剩余的字符数，则只返回剩余的字符，而不会为读取的字符串填充任何内容来满足 *NumChar* 所指定的长度。如果没有字符可读取，则返回空值变量。**ReadText** 不能用来反向读取。</span><span class="sxs-lookup"><span data-stu-id="6c395-p102">If *NumChar* is more than the number of characters left in the stream, only the characters remaining are returned. The string read is not padded to match the length specified by *NumChar*. If there are no characters left to read, a variant whose value is null is returned. **ReadText** cannot be used to read backwards.</span></span>


> [!NOTE]
> <P><span data-ttu-id="6c395-p103"><STRONG>ReadText</STRONG> 方法用于文本流（<A href="type-property-ado-stream.md">Type</A> 为 <STRONG>adTypeText</STRONG>）。对于二进制流（<STRONG>Type</STRONG> 为 <STRONG>adTypeBinary</STRONG>），请使用 <A href="read-method-ado.md">Read</A>。</span><span class="sxs-lookup"><span data-stu-id="6c395-p103">The <STRONG>ReadText</STRONG> method is used with text streams (<A href="type-property-ado-stream.md">Type</A> is <STRONG>adTypeText</STRONG>). For binary streams (<STRONG>Type</STRONG> is <STRONG>adTypeBinary</STRONG>), use <A href="read-method-ado.md">Read</A>.</span></span></P>

