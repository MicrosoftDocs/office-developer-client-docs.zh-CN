---
title: WriteText 方法 (ADO)
TOCTitle: WriteText method (ADO)
ms:assetid: 1ca2d9d5-11f4-d088-6fc3-53240208bb09
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248963(v=office.15)
ms:contentKeyID: 48543574
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6aecdbee544d3b30a6f6386c98d3083bb1167539
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949801"
---
# <a name="writetext-method-ado"></a><span data-ttu-id="41d3e-102">WriteText 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="41d3e-102">WriteText method (ADO)</span></span>

<span data-ttu-id="41d3e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="41d3e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="41d3e-104">用于将指定的文本字符串写入 [Stream](stream-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="41d3e-104">Writes a specified text string to a [Stream](stream-object-ado.md) object.</span></span>

## <a name="syntax"></a><span data-ttu-id="41d3e-105">语法</span><span class="sxs-lookup"><span data-stu-id="41d3e-105">Syntax</span></span>

<span data-ttu-id="41d3e-106">*流*。WriteText*数据\*\*选项*</span><span class="sxs-lookup"><span data-stu-id="41d3e-106">*Stream*.WriteText*Data*, *Options*</span></span>

## <a name="parameters"></a><span data-ttu-id="41d3e-107">参数</span><span class="sxs-lookup"><span data-stu-id="41d3e-107">Parameters</span></span>

|<span data-ttu-id="41d3e-108">参数</span><span class="sxs-lookup"><span data-stu-id="41d3e-108">Parameter</span></span>|<span data-ttu-id="41d3e-109">说明</span><span class="sxs-lookup"><span data-stu-id="41d3e-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="41d3e-110">*Data*</span><span class="sxs-lookup"><span data-stu-id="41d3e-110">*Data*</span></span> |<span data-ttu-id="41d3e-111">**String** 值，包含要写入的字符文本。</span><span class="sxs-lookup"><span data-stu-id="41d3e-111">A **String** value that contains the text in characters to be written.</span></span>|
|<span data-ttu-id="41d3e-112">*Options*</span><span class="sxs-lookup"><span data-stu-id="41d3e-112">*Options*</span></span> |<span data-ttu-id="41d3e-p101">可选。[StreamWriteEnum](streamwriteenum.md) 值，指定是否必须在指定的字符串末尾写入行分隔符。</span><span class="sxs-lookup"><span data-stu-id="41d3e-p101">Optional. A [StreamWriteEnum](streamwriteenum.md) value that specifies whether a line separator character must be written at the end of the specified string.</span></span>|

## <a name="remarks"></a><span data-ttu-id="41d3e-115">备注</span><span class="sxs-lookup"><span data-stu-id="41d3e-115">Remarks</span></span>

<span data-ttu-id="41d3e-116">指定的字符串被写入 **Stream** 对象中，且每个字符串之间不会有任何用于分隔的空格或字符。</span><span class="sxs-lookup"><span data-stu-id="41d3e-116">Specified strings are written to the **Stream** object without any intervening spaces or characters between each string.</span></span>

<span data-ttu-id="41d3e-p102">当前 [Position](position-property-ado.md) 被设置为写入数据后的字符处。 **WriteText** 方法不会将流中剩下的数据截断。如果希望截断这些字符，请调用 [SetEOS](seteos-method-ado.md)。</span><span class="sxs-lookup"><span data-stu-id="41d3e-p102">The current [Position](position-property-ado.md) is set to the character following the written data. The **WriteText** method does not truncate the rest of the data in a stream. If you want to truncate these characters, call [SetEOS](seteos-method-ado.md).</span></span>

<span data-ttu-id="41d3e-120">如果写入的数据超过了当前 [EOS](eos-property-ado.md) 位置， [Stream](https://msdn.microsoft.com/library/jj250128\(v=office.15\)) 的 **Size** 会增加，以包含所有新字符，并且 **EOS** 将移动到 **Stream** 中新的最后字节处。</span><span class="sxs-lookup"><span data-stu-id="41d3e-120">If you write past the current [EOS](eos-property-ado.md) position, the [Size](https://msdn.microsoft.com/library/jj250128\(v=office.15\)) of the **Stream** will be increased to contain any new characters, and **EOS** will move to the new last byte in the **Stream**.</span></span>

> [!NOTE]
> <span data-ttu-id="41d3e-p103">**WriteText** 方法用于文本流（[Type](type-property-ado-stream.md) 为 **adTypeText**）。对于二进制流（**Type** 为 **adTypeBinary**），请使用 [Write](write-method-ado.md)。</span><span class="sxs-lookup"><span data-stu-id="41d3e-p103">The **WriteText** method is used with text streams ([Type](type-property-ado-stream.md) is **adTypeText**). For binary streams (**Type** is **adTypeBinary**), use [Write](write-method-ado.md).</span></span>


