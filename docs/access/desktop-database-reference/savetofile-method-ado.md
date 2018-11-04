---
title: SaveToFile 方法 (ADO)
TOCTitle: SaveToFile method (ADO)
ms:assetid: db0fd95e-8ef3-af87-5346-8f8713153ca7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250104(v=office.15)
ms:contentKeyID: 48548097
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: df7545b9abd29571788a0bbfc69323ec31e75f65
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949808"
---
# <a name="savetofile-method-ado"></a><span data-ttu-id="21a1a-102">SaveToFile 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="21a1a-102">SaveToFile method (ADO)</span></span>

<span data-ttu-id="21a1a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="21a1a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="21a1a-104">可将 [Stream](stream-object-ado.md) 的二进制内容保存到文件。</span><span class="sxs-lookup"><span data-stu-id="21a1a-104">Saves the binary contents of a [Stream](stream-object-ado.md) to a file.</span></span>

## <a name="syntax"></a><span data-ttu-id="21a1a-105">语法</span><span class="sxs-lookup"><span data-stu-id="21a1a-105">Syntax</span></span>

<span data-ttu-id="21a1a-106">*流*。SaveToFile*文件名* *SaveOptions*</span><span class="sxs-lookup"><span data-stu-id="21a1a-106">*Stream*.SaveToFile*FileName*, *SaveOptions*</span></span>

## <a name="parameters"></a><span data-ttu-id="21a1a-107">参数</span><span class="sxs-lookup"><span data-stu-id="21a1a-107">Parameters</span></span>

|<span data-ttu-id="21a1a-108">参数</span><span class="sxs-lookup"><span data-stu-id="21a1a-108">Parameter</span></span>|<span data-ttu-id="21a1a-109">说明</span><span class="sxs-lookup"><span data-stu-id="21a1a-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="21a1a-110">*FileName*</span><span class="sxs-lookup"><span data-stu-id="21a1a-110">*FileName*</span></span> |<span data-ttu-id="21a1a-p101">**字符串型** 值，包含要保存 **Stream** 内容的文件的完全限定名称。可以保存到任意一个有效的本地位置或可通过 UNC 值访问的任意位置。</span><span class="sxs-lookup"><span data-stu-id="21a1a-p101">A **String** value that contains the fully-qualified name of the file to which the contents of the **Stream** will be saved. You can save to any valid local location, or any location you have access to via a UNC value.</span></span>|
|<span data-ttu-id="21a1a-113">*SaveOptions*</span><span class="sxs-lookup"><span data-stu-id="21a1a-113">*SaveOptions*</span></span> |<span data-ttu-id="21a1a-p102">[SaveOptionsEnum](saveoptionsenum.md) 值，指定 **SaveToFile** 是否应在文件不存在时创建新文件。默认值为 **adSaveCreateNotExists** 。通过这些选项，可以指定当指定文件不存在时引发错误。还可以指定 **SaveToFile** 覆盖现有文件的当前内容。</span><span class="sxs-lookup"><span data-stu-id="21a1a-p102">A [SaveOptionsEnum](saveoptionsenum.md) value that specifies whether a new file should be created by **SaveToFile**, if it does not already exist. Default value is **adSaveCreateNotExists**. With these options you can specify that an error occurs if the specified file does not exist. You can also specify that **SaveToFile** overwrites the current contents of an existing file.</span></span>|

> [!NOTE]
> <span data-ttu-id="21a1a-118">[!注释] 如果覆盖现有文件（在设置 **adSaveCreateOverwrite** 时），则 **SaveToFile** 会从覆盖之前的原文件中截去新的 [EOS](eos-property-ado.md) 之后的所有字节。</span><span class="sxs-lookup"><span data-stu-id="21a1a-118">If you overwrite an existing file (when **adSaveCreateOverwrite** is set), **SaveToFile** truncates any bytes from the original existing file that follow the new [EOS](eos-property-ado.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="21a1a-119">备注</span><span class="sxs-lookup"><span data-stu-id="21a1a-119">Remarks</span></span>

<span data-ttu-id="21a1a-p103">**SaveToFile** 可以用于将 **Stream** 对象的内容复制到本地文件。 **Stream** 对象的内容或属性都不会发生变化。在调用 **SaveToFile** 之前，必须打开 **Stream** 对象。</span><span class="sxs-lookup"><span data-stu-id="21a1a-p103">**SaveToFile** may be used to copy the contents of a **Stream** object to a local file. There is no change in the contents or properties of the **Stream** object. The **Stream** object must be open before calling **SaveToFile**.</span></span>

<span data-ttu-id="21a1a-p104">此方法不会更改 **Stream** 对象与其基础源之间的关联性。 **Stream** 对象将仍与打开时作为其来源的原始 URL 或 **Record** 相关联。</span><span class="sxs-lookup"><span data-stu-id="21a1a-p104">This method does not change the association of the **Stream** object to its underlying source. The **Stream** object will still be associated with the original URL or **Record** that was its source when opened.</span></span>

<span data-ttu-id="21a1a-125">在 **SaveToFile** 操作之后，流中的当前位置（[Position 属性 (ADO)](position-property-ado.md)）设置为流的开头 (0)。</span><span class="sxs-lookup"><span data-stu-id="21a1a-125">After a **SaveToFile** operation, the current position ([Position](position-property-ado.md)) in the stream is set to the beginning of the stream (0).</span></span>

