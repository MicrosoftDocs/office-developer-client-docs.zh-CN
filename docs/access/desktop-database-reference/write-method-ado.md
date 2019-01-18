---
title: 编写方法-ActiveX 数据对象 (ADO)
TOCTitle: Write method (ADO)
ms:assetid: cabe4581-409f-7f05-bd59-d495bfb2c6fd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249986(v=office.15)
ms:contentKeyID: 48547697
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c6f4bba55ec3a32d206d3a7bfd001e96cd94923e
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28702514"
---
# <a name="write-method-ado"></a><span data-ttu-id="040cc-102">Write 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="040cc-102">Write method (ADO)</span></span>

<span data-ttu-id="040cc-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="040cc-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="040cc-104">用于将二进制数据写入 [Stream](stream-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="040cc-104">Writes binary data to a [Stream](stream-object-ado.md) object.</span></span>

## <a name="syntax"></a><span data-ttu-id="040cc-105">语法</span><span class="sxs-lookup"><span data-stu-id="040cc-105">Syntax</span></span>

<span data-ttu-id="040cc-106">*流*。编写*缓冲区*</span><span class="sxs-lookup"><span data-stu-id="040cc-106">*Stream*.Write*Buffer*</span></span>

## <a name="parameters"></a><span data-ttu-id="040cc-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="040cc-107">Parameters</span></span>

|<span data-ttu-id="040cc-108">参数</span><span class="sxs-lookup"><span data-stu-id="040cc-108">Parameter</span></span>|<span data-ttu-id="040cc-109">说明</span><span class="sxs-lookup"><span data-stu-id="040cc-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="040cc-110">*Buffer*</span><span class="sxs-lookup"><span data-stu-id="040cc-110">*Buffer*</span></span> |<span data-ttu-id="040cc-111">包含要写入的字节数组的 **Variant** 。</span><span class="sxs-lookup"><span data-stu-id="040cc-111">A **Variant** that contains an array of bytes to be written.</span></span>|

## <a name="remarks"></a><span data-ttu-id="040cc-112">备注</span><span class="sxs-lookup"><span data-stu-id="040cc-112">Remarks</span></span>

<span data-ttu-id="040cc-113">指定字节被写入 **Stream** 对象，且各字节之间不会插入空格。</span><span class="sxs-lookup"><span data-stu-id="040cc-113">Specified bytes are written to the **Stream** object without any intervening spaces between each byte.</span></span>

<span data-ttu-id="040cc-p101">当前 [Position](position-property-ado.md) 被设置为写入数据后的字节。 **Write** 方法不会将某个流中剩下的数据截断。如果希望截断这些字节，请调用 [SetEOS](seteos-method-ado.md)。</span><span class="sxs-lookup"><span data-stu-id="040cc-p101">The current [Position](position-property-ado.md) is set to the byte following the written data. The **Write** method does not truncate the rest of the data in a stream. If you want to truncate these bytes, call [SetEOS](seteos-method-ado.md).</span></span>

<span data-ttu-id="040cc-117">如果写入的数据超过了当前 [EOS](eos-property-ado.md) 位置，则 [Stream](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/size-property-ado-stream) 的 **Size** 会增加，以包含所有新字节，并且 **EOS** 将移动到 **Stream** 中新的最后一个字节。</span><span class="sxs-lookup"><span data-stu-id="040cc-117">If you write past the current [EOS](eos-property-ado.md) position, the [Size](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/size-property-ado-stream) of the **Stream** will be increased to contain any new bytes, and **EOS** will move to the new last byte in the **Stream**.</span></span>

> [!NOTE]
> <span data-ttu-id="040cc-p102">**Write** 方法用于二进制流（[Type](type-property-ado-stream.md) 为 **adTypeBinary**）。对于文本流（**Type** 为 **adTypeText**），请使用 [WriteText](writetext-method-ado.md)。</span><span class="sxs-lookup"><span data-stu-id="040cc-p102">The **Write** method is used with binary streams ([Type](type-property-ado-stream.md) is **adTypeBinary**). For text streams (**Type** is **adTypeText**), use [WriteText](writetext-method-ado.md).</span></span>

