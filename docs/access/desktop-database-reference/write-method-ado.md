---
title: 编写方法-ActiveX 数据对象 (ADO)
TOCTitle: Write Method (ADO)
ms:assetid: cabe4581-409f-7f05-bd59-d495bfb2c6fd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249986(v=office.15)
ms:contentKeyID: 48547697
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 98af810c9a24d38a6b2b32db31f9a650c2d6f70a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468281"
---
# <a name="write-method-ado"></a><span data-ttu-id="12806-102">Write 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="12806-102">Write Method (ADO)</span></span>


<span data-ttu-id="12806-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="12806-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="12806-104">用于将二进制数据写入 [Stream](stream-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="12806-104">Writes binary data to a [Stream](stream-object-ado.md) object.</span></span>

## <a name="syntax"></a><span data-ttu-id="12806-105">语法</span><span class="sxs-lookup"><span data-stu-id="12806-105">Syntax</span></span>

<span data-ttu-id="12806-106">*流*。编写*缓冲区*</span><span class="sxs-lookup"><span data-stu-id="12806-106">*Stream*.Write*Buffer*</span></span>

## <a name="parameters"></a><span data-ttu-id="12806-107">参数</span><span class="sxs-lookup"><span data-stu-id="12806-107">Parameters</span></span>

  - <span data-ttu-id="12806-108">*Buffer*</span><span class="sxs-lookup"><span data-stu-id="12806-108">*Buffer*</span></span>

  - <span data-ttu-id="12806-109">包含要写入的字节数组的 **Variant** 。</span><span class="sxs-lookup"><span data-stu-id="12806-109">A **Variant** that contains an array of bytes to be written.</span></span>

## <a name="remarks"></a><span data-ttu-id="12806-110">备注</span><span class="sxs-lookup"><span data-stu-id="12806-110">Remarks</span></span>

<span data-ttu-id="12806-111">指定字节被写入 **Stream** 对象，且各字节之间不会插入空格。</span><span class="sxs-lookup"><span data-stu-id="12806-111">Specified bytes are written to the **Stream** object without any intervening spaces between each byte.</span></span>

<span data-ttu-id="12806-p101">当前 [Position](position-property-ado.md) 被设置为写入数据后的字节。 **Write** 方法不会将某个流中剩下的数据截断。如果希望截断这些字节，请调用 [SetEOS](seteos-method-ado.md)。</span><span class="sxs-lookup"><span data-stu-id="12806-p101">The current [Position](position-property-ado.md) is set to the byte following the written data. The **Write** method does not truncate the rest of the data in a stream. If you want to truncate these bytes, call [SetEOS](seteos-method-ado.md).</span></span>

<span data-ttu-id="12806-115">如果写入的数据超过了当前 [EOS](eos-property-ado.md) 位置，则 [Stream](https://msdn.microsoft.com/library/jj250128\(v=office.15\)) 的 **Size** 会增加，以包含所有新字节，并且 **EOS** 将移动到 **Stream** 中新的最后一个字节。</span><span class="sxs-lookup"><span data-stu-id="12806-115">If you write past the current [EOS](eos-property-ado.md) position, the [Size](https://msdn.microsoft.com/library/jj250128\(v=office.15\)) of the **Stream** will be increased to contain any new bytes, and **EOS** will move to the new last byte in the **Stream**.</span></span>


> [!NOTE]
> <P><span data-ttu-id="12806-p102"><STRONG>Write</STRONG> 方法用于二进制流（<A href="type-property-ado-stream.md">Type</A> 为 <STRONG>adTypeBinary</STRONG>）。对于文本流（<STRONG>Type</STRONG> 为 <STRONG>adTypeText</STRONG>），请使用 <A href="writetext-method-ado.md">WriteText</A>。</span><span class="sxs-lookup"><span data-stu-id="12806-p102">The <STRONG>Write</STRONG> method is used with binary streams (<A href="type-property-ado-stream.md">Type</A> is <STRONG>adTypeBinary</STRONG>). For text streams (<STRONG>Type</STRONG> is <STRONG>adTypeText</STRONG>), use <A href="writetext-method-ado.md">WriteText</A>.</span></span></P>


