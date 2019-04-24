---
title: CopyTo 方法 (ADO)
TOCTitle: CopyTo method (ADO)
ms:assetid: 1c1ab950-51f7-7ecc-ccd8-e689db02f06a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248958(v=office.15)
ms:contentKeyID: 48543558
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2e8de2caf2abc53b0dbd014f21a85a6d54749033
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295476"
---
# <a name="copyto-method-ado"></a><span data-ttu-id="c3e57-102">CopyTo 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="c3e57-102">CopyTo method (ADO)</span></span>

<span data-ttu-id="c3e57-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="c3e57-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c3e57-104">用于将 [Stream](stream-object-ado.md) 中指定数量的字符或字节（取决于[类型](type-property-ado-stream.md)）复制到另一个 **Stream** 对象。</span><span class="sxs-lookup"><span data-stu-id="c3e57-104">Copies the specified number of characters or bytes (depending on [Type](type-property-ado-stream.md)) in the [Stream](stream-object-ado.md) to another **Stream** object.</span></span>

## <a name="syntax"></a><span data-ttu-id="c3e57-105">语法</span><span class="sxs-lookup"><span data-stu-id="c3e57-105">Syntax</span></span>

<span data-ttu-id="c3e57-106">*Stream*。CopyTo *DestStream*、 *NumChars*</span><span class="sxs-lookup"><span data-stu-id="c3e57-106">*Stream*.CopyTo *DestStream*, *NumChars*</span></span>

## <a name="parameters"></a><span data-ttu-id="c3e57-107">参数</span><span class="sxs-lookup"><span data-stu-id="c3e57-107">Parameters</span></span>

|<span data-ttu-id="c3e57-108">参数</span><span class="sxs-lookup"><span data-stu-id="c3e57-108">Parameter</span></span>|<span data-ttu-id="c3e57-109">描述</span><span class="sxs-lookup"><span data-stu-id="c3e57-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="c3e57-110">*DestStream*</span><span class="sxs-lookup"><span data-stu-id="c3e57-110">*DestStream*</span></span> |<span data-ttu-id="c3e57-111">对象变量值，包含对打开的 **Stream** 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="c3e57-111">An object variable value that contains a reference to an open **Stream** object.</span></span> <span data-ttu-id="c3e57-112">当前 **Stream** 复制到由 *DestStream* 指定的目标 **Stream**。</span><span class="sxs-lookup"><span data-stu-id="c3e57-112">The current **Stream** is copied to the destination **Stream** specified by *DestStream*.</span></span> <span data-ttu-id="c3e57-113">目标 **Stream** 必须已经打开。</span><span class="sxs-lookup"><span data-stu-id="c3e57-113">The destination **Stream** must already be open.</span></span> <span data-ttu-id="c3e57-114">否则，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="c3e57-114">If not, a run-time error occurs.</span></span><br/><br/><span data-ttu-id="c3e57-115">**注意**: *DestStream*参数可能不是**stream**对象的代理, 因为这需要访问**stream**对象上无法远程访问客户端的专用接口。</span><span class="sxs-lookup"><span data-stu-id="c3e57-115">**NOTE**: The *DestStream* parameter may not be a proxy of the **Stream** object because this requires access to a private interface on the **Stream** object that cannot be remoted to the client.</span></span>|
|<span data-ttu-id="c3e57-116">*NumChars*</span><span class="sxs-lookup"><span data-stu-id="c3e57-116">*NumChars*</span></span> |<span data-ttu-id="c3e57-p102">可选。**整型**值，指定要从源 **Stream** 中的当前位置复制到目标 **Stream** 的字节或字符的数量。默认值为 –1，指定复制从当前位置到 [EOS](eos-property-ado.md) 之间的所有字符或字节。</span><span class="sxs-lookup"><span data-stu-id="c3e57-p102">Optional. An **Integer** value that specifies the number of bytes or characters to be copied from the current position in the source **Stream** to the destination **Stream**. The default value is –1, which specifies that all characters or bytes are copied from the current position to [EOS](eos-property-ado.md).</span></span>|

## <a name="remarks"></a><span data-ttu-id="c3e57-120">注解</span><span class="sxs-lookup"><span data-stu-id="c3e57-120">Remarks</span></span>

<span data-ttu-id="c3e57-p103">该方法从当前位置（由 [Position](position-property-ado.md) 属性指定）开始复制指定数量的字符或字节。如果指定的数目超过了 **EOS** 之前的可用字节数，则仅复制从当前位置到 **EOS** 之间的字符或字节。如果 *NumChars* 的值为 –1，或者省略该值，则从当前位置开始复制所有字符或字节。</span><span class="sxs-lookup"><span data-stu-id="c3e57-p103">This method copies the specified number of characters or bytes, starting from the current position specified by the [Position](position-property-ado.md) property. If the specified number is more than the available number of bytes until **EOS**, then only characters or bytes from the current position to **EOS** are copied. If the value of *NumChars* is –1, or omitted, all characters or bytes starting from the current position are copied.</span></span>

<span data-ttu-id="c3e57-p104">如果目标流中已经有字符或字节，则复制内容末尾以外的所有内容将保留而不会被截去。 **Position** 成为紧跟在所复制的最后一个字节之后的字节。如果要截去这些字节，请调用 [SetEOS](seteos-method-ado.md)。</span><span class="sxs-lookup"><span data-stu-id="c3e57-p104">If there are existing characters or bytes in the destination stream, all contents beyond the point where the copy ends remain, and are not truncated. **Position** becomes the byte immediately following the last byte copied. If you want to truncate these bytes, call [SetEOS](seteos-method-ado.md).</span></span>

<span data-ttu-id="c3e57-p105">应使用 **CopyTo** 将数据复制到与源 **Stream** 类型相同的目标 **Stream** （它们的 **Type** 属性设置都为 **adTypeText** 或都为 **adTypeBinary**）。对于文本 **Stream** 对象，您可以将目标 **Stream** 的 [Charset](charset-property-ado.md) 属性设置更改为从一个字符集转换为另一个字符集。另外，文本 **Stream** 对象可以成功复制到二进制 **Stream** 对象中，但二进制 **Stream** 对象不能复制到文本 **Stream** 对象中。</span><span class="sxs-lookup"><span data-stu-id="c3e57-p105">**CopyTo** should be used to copy data to a destination **Stream** of the same type as the source **Stream** (their **Type** property settings are both **adTypeText** or both **adTypeBinary**). For text **Stream** objects, you can change the [Charset](charset-property-ado.md) property setting of the destination **Stream** to translate from one character set to another. Also, text **Stream** objects can be successfully copied into binary **Stream** objects, but binary **Stream** objects cannot be copied into text **Stream** objects.</span></span>

