---
title: PropertyDefinition 流示例
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 7919f4d7-04df-4a96-a5b1-b7b460890486
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 63a8141221c0ff7a8c6ffee20587b682386f87b5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328502"
---
# <a name="propertydefinition-stream-sample"></a><span data-ttu-id="a8484-103">PropertyDefinition 流示例</span><span class="sxs-lookup"><span data-stu-id="a8484-103">PropertyDefinition stream sample</span></span>

<span data-ttu-id="a8484-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a8484-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a8484-105">本主题介绍 PropertyDefinition 流的示例。</span><span class="sxs-lookup"><span data-stu-id="a8484-105">This topic describes an example of a PropertyDefinition stream.</span></span> <span data-ttu-id="a8484-106">流包含用户定义的字段的定义`TextField1`。</span><span class="sxs-lookup"><span data-stu-id="a8484-106">The stream contains a definition of a user-defined field,  `TextField1`.</span></span> <span data-ttu-id="a8484-107">类型为**Text**, 定义为 PropDefV2 格式。</span><span class="sxs-lookup"><span data-stu-id="a8484-107">The type is **Text**, and the definition is in the PropDefV2 format.</span></span>
  
## <a name="data-dump"></a><span data-ttu-id="a8484-108">数据转储</span><span class="sxs-lookup"><span data-stu-id="a8484-108">Data dump</span></span>

<span data-ttu-id="a8484-109">以下是流的数据转储, 因为它将显示在二进制编辑器中。</span><span class="sxs-lookup"><span data-stu-id="a8484-109">The following is a data dump of the stream as it would be displayed in a binary editor.</span></span>
  
|<span data-ttu-id="a8484-110">流偏移量</span><span class="sxs-lookup"><span data-stu-id="a8484-110">Stream offset</span></span>|<span data-ttu-id="a8484-111">数据字节</span><span class="sxs-lookup"><span data-stu-id="a8484-111">Data bytes</span></span>|<span data-ttu-id="a8484-112">ASCII 数据</span><span class="sxs-lookup"><span data-stu-id="a8484-112">ASCII data</span></span>|
|:-----|:-----|:-----|
| `0000000000` <br/> | `03 01 01 00 00 00 45 00 00 00 08 00 00 00 00 00` <br/> | `???...E...?.....` <br/> |
| `0000000010` <br/> | `0A 00 54 00 65 00 78 00 74 00 46 00 69 00 65 00` <br/> | `?.T.e.x.t.F.i.e.` <br/> |
| `0000000020` <br/> | `6C 00 64 00 31 00 0A 54 65 78 74 46 69 65 6C 64` <br/> | `l.d.1.?TextField` <br/> |
| `0000000030` <br/> | `31 00 00 00 00 00 00 00 00 15 00 00 00 0A 54 00` <br/> | `1........?...?T.` <br/> |
| `0000000040` <br/> | `65 00 78 00 74 00 46 00 69 00 65 00 6C 00 64 00` <br/> | `e.x.t.F.i.e.l.d.` <br/> |
| `0000000050` <br/> | `31 00 00 00 00 00` <br/> | `1.....` <br/> |
   
<span data-ttu-id="a8484-113">以下是对 PropertyDefinition 流的示例数据的分析:</span><span class="sxs-lookup"><span data-stu-id="a8484-113">The following is a parse of the sample data for the PropertyDefinition stream:</span></span>
  
- <span data-ttu-id="a8484-114">Version: Offset 0x0, 2 个字节: 0x0103 (PropDefV2)。</span><span class="sxs-lookup"><span data-stu-id="a8484-114">Version: Offset 0x0, 2 bytes: 0x0103 (PropDefV2).</span></span>
    
- <span data-ttu-id="a8484-115">FieldDefinitionCount: 偏移 0x2, 4 个字节: 0x1 (1)。</span><span class="sxs-lookup"><span data-stu-id="a8484-115">FieldDefinitionCount: Offset 0x2, 4 bytes: 0x1 (1).</span></span>
    
- <span data-ttu-id="a8484-116">FieldDefinitions: 偏移量 0x6, 1 FieldDefinition stream。</span><span class="sxs-lookup"><span data-stu-id="a8484-116">FieldDefinitions: Offset 0x6, array of 1 FieldDefinition stream.</span></span>
    
  - <span data-ttu-id="a8484-117">Flags: Offset 0x6, 4 个字节: 0x45 (PDO_IS_CUSTOM |PDO_PRINT_SAVEAS |PDO_PRINT_SAVEAS_DEF)。</span><span class="sxs-lookup"><span data-stu-id="a8484-117">Flags: Offset 0x6, 4 bytes: 0x45 (PDO_IS_CUSTOM|PDO_PRINT_SAVEAS|PDO_PRINT_SAVEAS_DEF).</span></span>
    
  - <span data-ttu-id="a8484-118">VT: 偏移量 0xA, 2 个字节: 0x8 (**VT_BSTR**)。</span><span class="sxs-lookup"><span data-stu-id="a8484-118">VT: Offset 0xA, 2 bytes: 0x8 (**VT_BSTR**).</span></span>
    
  - <span data-ttu-id="a8484-119">DispId: 偏移量 0xC, 4 个字节: 0x0 (0)。</span><span class="sxs-lookup"><span data-stu-id="a8484-119">DispId: Offset 0xC, 4 bytes: 0x0 (0).</span></span>
    
  - <span data-ttu-id="a8484-120">NmidNameLength: Offset 0x10, 2 个字节: 0xA (10)。</span><span class="sxs-lookup"><span data-stu-id="a8484-120">NmidNameLength: Offset 0x10, 2 bytes: 0xA (10).</span></span>
    
  - <span data-ttu-id="a8484-121">NmidName: 偏移量 0x12, 10 WCHARs 数组。</span><span class="sxs-lookup"><span data-stu-id="a8484-121">NmidName: Offset 0x12, array of 10 WCHARs.</span></span> <span data-ttu-id="a8484-122">Unicode 字符串值: "TextField1"。</span><span class="sxs-lookup"><span data-stu-id="a8484-122">Unicode string value: "TextField1".</span></span>
    
  - <span data-ttu-id="a8484-123">NameANSI: 偏移量 0x26, PackedAnsiString stream。</span><span class="sxs-lookup"><span data-stu-id="a8484-123">NameANSI: Offset 0x26, PackedAnsiString stream.</span></span>
    
    - <span data-ttu-id="a8484-124">Length: 偏移量 0x26, 1 个字节: 0xA (10)。</span><span class="sxs-lookup"><span data-stu-id="a8484-124">Length: Offset 0x26, 1 byte: 0xA (10).</span></span>
      
    - <span data-ttu-id="a8484-125">字符: 偏移 0x27, 数组为10个字符。</span><span class="sxs-lookup"><span data-stu-id="a8484-125">Characters: Offset 0x27, array of 10 CHARs.</span></span> <span data-ttu-id="a8484-126">ANSI 字符串值: "TextField1"。</span><span class="sxs-lookup"><span data-stu-id="a8484-126">ANSI string value: "TextField1".</span></span>
    
  - <span data-ttu-id="a8484-127">FormulaANSI: 偏移量 0x31, PackedAnsiString stream。</span><span class="sxs-lookup"><span data-stu-id="a8484-127">FormulaANSI: Offset 0x31, PackedAnsiString stream.</span></span>
    
    - <span data-ttu-id="a8484-128">Length: 偏移量 0x31, 1 个字节: 0x0 (0)。</span><span class="sxs-lookup"><span data-stu-id="a8484-128">Length: Offset 0x31, 1 byte: 0x0 (0).</span></span>
      
    - <span data-ttu-id="a8484-129">字符: 偏移量 0x32, 0 个字符数组。</span><span class="sxs-lookup"><span data-stu-id="a8484-129">Characters: Offset 0x32, array of 0 CHARs.</span></span> <span data-ttu-id="a8484-130">空 ANSI 字符串。</span><span class="sxs-lookup"><span data-stu-id="a8484-130">Empty ANSI string.</span></span>
    
  - <span data-ttu-id="a8484-131">ValidationRuleANSI: 偏移量 0x32, PackedAnsiString stream。</span><span class="sxs-lookup"><span data-stu-id="a8484-131">ValidationRuleANSI: Offset 0x32, PackedAnsiString stream.</span></span>
    
    - <span data-ttu-id="a8484-132">Length: 偏移量 0x32, 1 个字节: 0x0 (0)。</span><span class="sxs-lookup"><span data-stu-id="a8484-132">Length: Offset 0x32, 1 byte: 0x0 (0).</span></span>
      
    - <span data-ttu-id="a8484-133">字符: 偏移量 0x33, 0 个字符数组。</span><span class="sxs-lookup"><span data-stu-id="a8484-133">Characters: Offset 0x33, array of 0 CHARs.</span></span> <span data-ttu-id="a8484-134">空 ANSI 字符串。</span><span class="sxs-lookup"><span data-stu-id="a8484-134">Empty ANSI string.</span></span>
    
  - <span data-ttu-id="a8484-135">ValidationTextANSI: 偏移量 0x33, PackedAnsiString stream。</span><span class="sxs-lookup"><span data-stu-id="a8484-135">ValidationTextANSI: Offset 0x33, PackedAnsiString stream.</span></span>
    
    - <span data-ttu-id="a8484-136">Length: 偏移量 0x33, 1 个字节: 0x0 (0)。</span><span class="sxs-lookup"><span data-stu-id="a8484-136">Length: Offset 0x33, 1 byte: 0x0 (0).</span></span>
      
    - <span data-ttu-id="a8484-137">字符: 偏移量 0x34, 0 个字符数组。</span><span class="sxs-lookup"><span data-stu-id="a8484-137">Characters: Offset 0x34, array of 0 CHARs.</span></span> <span data-ttu-id="a8484-138">空 ANSI 字符串。</span><span class="sxs-lookup"><span data-stu-id="a8484-138">Empty ANSI string.</span></span>
    
  - <span data-ttu-id="a8484-139">ErrorANSI: 偏移量 0x34, PackedAnsiString stream。</span><span class="sxs-lookup"><span data-stu-id="a8484-139">ErrorANSI: Offset 0x34, PackedAnsiString stream.</span></span>
    
    - <span data-ttu-id="a8484-140">Length: 偏移量 0x34, 1 个字节: 0x0 (0)。</span><span class="sxs-lookup"><span data-stu-id="a8484-140">Length: Offset 0x34, 1 byte: 0x0 (0).</span></span>
      
    - <span data-ttu-id="a8484-141">字符: 偏移量 0x35, 0 个字符数组。</span><span class="sxs-lookup"><span data-stu-id="a8484-141">Characters: Offset 0x35, array of 0 CHARs.</span></span> <span data-ttu-id="a8484-142">空 ANSI 字符串。</span><span class="sxs-lookup"><span data-stu-id="a8484-142">Empty ANSI string.</span></span>
    
  - <span data-ttu-id="a8484-143">InternalType: 偏移量 0x35, 4 个字节: 0x0 (iTypeString)。</span><span class="sxs-lookup"><span data-stu-id="a8484-143">InternalType: Offset 0x35, 4 bytes: 0x0 (iTypeString).</span></span>
    
  - <span data-ttu-id="a8484-144">SkipBlocks: 偏移量 0x39, 系列的 SkipBlock 流。</span><span class="sxs-lookup"><span data-stu-id="a8484-144">SkipBlocks: Offset 0x39, series of SkipBlock streams.</span></span>
    
  - <span data-ttu-id="a8484-145">第一个 SkipBlock</span><span class="sxs-lookup"><span data-stu-id="a8484-145">First SkipBlock</span></span>
    
    - <span data-ttu-id="a8484-146">大小: 偏移 0x39, 4 个字节: 0x15 (21)。</span><span class="sxs-lookup"><span data-stu-id="a8484-146">Size: Offset 0x39, 4 bytes: 0x15 (21).</span></span>
      
    - <span data-ttu-id="a8484-147">内容: 偏移 0x3D, 数组为21字节。</span><span class="sxs-lookup"><span data-stu-id="a8484-147">Content: Offset 0x3D, array of 21 bytes.</span></span> <span data-ttu-id="a8484-148">这是第一个 SkipBlock 流, 因此此数组包含一个 FirstSkipBlockContent 流。</span><span class="sxs-lookup"><span data-stu-id="a8484-148">This is the first SkipBlock stream, so this array contains a FirstSkipBlockContent stream.</span></span>
      
      - <span data-ttu-id="a8484-149">FieldName: Offset 0x3D, PackedUnicodeString stream。</span><span class="sxs-lookup"><span data-stu-id="a8484-149">FieldName: Offset 0x3D, PackedUnicodeString stream.</span></span>
        
        - <span data-ttu-id="a8484-150">Length: 偏移量 0x3D, 1 个字节: 0xA (10)。</span><span class="sxs-lookup"><span data-stu-id="a8484-150">Length: Offset 0x3D, 1 byte: 0xA (10).</span></span>
          
        - <span data-ttu-id="a8484-151">字符: 偏移 0x3E, 数组为 10 WCHARs。</span><span class="sxs-lookup"><span data-stu-id="a8484-151">Characters: Offset 0x3E, array of 10 WCHARs.</span></span> <span data-ttu-id="a8484-152">Unicode 字符串值: "TextField1"。</span><span class="sxs-lookup"><span data-stu-id="a8484-152">Unicode string value: "TextField1".</span></span>
    
  - <span data-ttu-id="a8484-153">第二个 SkipBlock</span><span class="sxs-lookup"><span data-stu-id="a8484-153">Second SkipBlock</span></span>
    
    - <span data-ttu-id="a8484-154">大小: 偏移 0x52, 4 个字节: 0x0 (0)。</span><span class="sxs-lookup"><span data-stu-id="a8484-154">Size: Offset 0x52, 4 bytes: 0x0 (0).</span></span> <span data-ttu-id="a8484-155">这是终止的 SkipBlock 流。</span><span class="sxs-lookup"><span data-stu-id="a8484-155">This is the terminating SkipBlock stream.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a8484-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8484-156">See also</span></span>

- [<span data-ttu-id="a8484-157">Outlook 项目和字段</span><span class="sxs-lookup"><span data-stu-id="a8484-157">Outlook Items and Fields</span></span>](outlook-items-and-fields.md)
- [<span data-ttu-id="a8484-158">流结构</span><span class="sxs-lookup"><span data-stu-id="a8484-158">Stream Structures</span></span>](stream-structures.md)
- [<span data-ttu-id="a8484-159">PropertyDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="a8484-159">PropertyDefinition Stream Structure</span></span>](propertydefinition-stream-structure.md)
- [<span data-ttu-id="a8484-160">FieldDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="a8484-160">FieldDefinition Stream Structure</span></span>](fielddefinition-stream-structure.md)
- [<span data-ttu-id="a8484-161">SkipBlock 流结构</span><span class="sxs-lookup"><span data-stu-id="a8484-161">SkipBlock Stream Structure</span></span>](skipblock-stream-structure.md)
- [<span data-ttu-id="a8484-162">FirstSkipBlockContent 流结构</span><span class="sxs-lookup"><span data-stu-id="a8484-162">FirstSkipBlockContent Stream Structure</span></span>](firstskipblockcontent-stream-structure.md)
- [<span data-ttu-id="a8484-163">PackedAnsiString 流结构</span><span class="sxs-lookup"><span data-stu-id="a8484-163">PackedAnsiString Stream Structure</span></span>](packedansistring-stream-structure.md)
- [<span data-ttu-id="a8484-164">PackedUnicodeString 流结构</span><span class="sxs-lookup"><span data-stu-id="a8484-164">PackedUnicodeString Stream Structure</span></span>](packedunicodestring-stream-structure.md)

