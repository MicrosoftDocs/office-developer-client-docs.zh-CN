---
title: Read 方法-ActiveX 数据对象 (ADO)
TOCTitle: Read method (ADO)
ms:assetid: 91c3ad34-f891-5be0-1fc1-c5c8a2ff07a4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249641(v=office.15)
ms:contentKeyID: 48546357
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 7ce545b1a6b036cae9f92d7e1ab7ba7479e4e252
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307670"
---
# <a name="read-method-ado"></a><span data-ttu-id="3491e-102">Read 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="3491e-102">Read method (ADO)</span></span>

<span data-ttu-id="3491e-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="3491e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="3491e-104">可从二进制 [Stream](stream-object-ado.md) 对象读取指定数量的字节。</span><span class="sxs-lookup"><span data-stu-id="3491e-104">Reads a specified number of bytes from a binary [Stream](stream-object-ado.md) object.</span></span>

## <a name="syntax"></a><span data-ttu-id="3491e-105">语法</span><span class="sxs-lookup"><span data-stu-id="3491e-105">Syntax</span></span>

<span data-ttu-id="3491e-106">*变体* = *流*。Read (*NumBytes* )</span><span class="sxs-lookup"><span data-stu-id="3491e-106">*Variant* = *Stream*.Read (*NumBytes* )</span></span>

## <a name="parameters"></a><span data-ttu-id="3491e-107">参数</span><span class="sxs-lookup"><span data-stu-id="3491e-107">Parameters</span></span>

|<span data-ttu-id="3491e-108">参数</span><span class="sxs-lookup"><span data-stu-id="3491e-108">Parameter</span></span>|<span data-ttu-id="3491e-109">描述</span><span class="sxs-lookup"><span data-stu-id="3491e-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="3491e-110">*NumBytes*</span><span class="sxs-lookup"><span data-stu-id="3491e-110">*NumBytes*</span></span> |<span data-ttu-id="3491e-p101">可选。 **长整型** 值，指定要从文件读取的字节数或 [StreamReadEnum](streamreadenum.md) 值 **adReadAll** ，后者为默认值。</span><span class="sxs-lookup"><span data-stu-id="3491e-p101">Optional. A **Long** value that specifies the number of bytes to read from the file or the [StreamReadEnum](streamreadenum.md) value **adReadAll**, which is the default.</span></span>|

## <a name="return-value"></a><span data-ttu-id="3491e-113">返回值</span><span class="sxs-lookup"><span data-stu-id="3491e-113">Return value</span></span>

<span data-ttu-id="3491e-114">**Read** 方法从 **Stream** 对象中读取指定数量的字节或整个流，并将结果数据以**变量型**格式返回。</span><span class="sxs-lookup"><span data-stu-id="3491e-114">The **Read** method reads a specified number of bytes or the entire stream from a **Stream** object and returns the resulting data as a **Variant**.</span></span>

## <a name="remarks"></a><span data-ttu-id="3491e-115">注解</span><span class="sxs-lookup"><span data-stu-id="3491e-115">Remarks</span></span>

<span data-ttu-id="3491e-p102">如果 *NumBytes* 大于 **Stream** 中剩余的字节数，则只返回剩余的字节，而不会为读取的数据填充任何内容来匹配 *NumBytes* 所指定的长度。如果没有字节可读取，则返回空值变量。**Read** 不能用来反向读取。</span><span class="sxs-lookup"><span data-stu-id="3491e-p102">If *NumBytes* is more than the number of bytes left in the **Stream**, only the bytes remaining are returned. The data read is not padded to match the length specified by *NumBytes*. If there are no bytes left to read, a variant with a null value is returned. **Read** cannot be used to read backwards.</span></span>

> [!NOTE]
> <span data-ttu-id="3491e-p103">*NumBytes* 始终会计量字节数。对于 **Stream** 对象（[Type](type-property-ado-stream.md) 为 **adTypeText**），请使用 [ReadText](readtext-method-ado.md)。</span><span class="sxs-lookup"><span data-stu-id="3491e-p103">*NumBytes* always measures bytes. For text **Stream** objects ([Type](type-property-ado-stream.md) is **adTypeText**), use [ReadText](readtext-method-ado.md).</span></span>


