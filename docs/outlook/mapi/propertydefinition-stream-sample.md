---
title: PropertyDefinition 流示例
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 7919f4d7-04df-4a96-a5b1-b7b460890486
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 63a8141221c0ff7a8c6ffee20587b682386f87b5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406659"
---
# <a name="propertydefinition-stream-sample"></a><span data-ttu-id="f3c70-103">PropertyDefinition 流示例</span><span class="sxs-lookup"><span data-stu-id="f3c70-103">PropertyDefinition stream sample</span></span>

<span data-ttu-id="f3c70-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f3c70-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f3c70-105">本主题介绍 PropertyDefinition 流的示例。</span><span class="sxs-lookup"><span data-stu-id="f3c70-105">This topic describes an example of a PropertyDefinition stream.</span></span> <span data-ttu-id="f3c70-106">流包含用户定义的字段的定义  `TextField1` 。</span><span class="sxs-lookup"><span data-stu-id="f3c70-106">The stream contains a definition of a user-defined field,  `TextField1`.</span></span> <span data-ttu-id="f3c70-107">类型为 **Text**，定义采用 PropDefV2 格式。</span><span class="sxs-lookup"><span data-stu-id="f3c70-107">The type is **Text**, and the definition is in the PropDefV2 format.</span></span>
  
## <a name="data-dump"></a><span data-ttu-id="f3c70-108">数据转储</span><span class="sxs-lookup"><span data-stu-id="f3c70-108">Data dump</span></span>

<span data-ttu-id="f3c70-109">下面是流的数据转储，就像在二进制编辑器中显示一样。</span><span class="sxs-lookup"><span data-stu-id="f3c70-109">The following is a data dump of the stream as it would be displayed in a binary editor.</span></span>
  
|<span data-ttu-id="f3c70-110">流偏移</span><span class="sxs-lookup"><span data-stu-id="f3c70-110">Stream offset</span></span>|<span data-ttu-id="f3c70-111">数据字节数</span><span class="sxs-lookup"><span data-stu-id="f3c70-111">Data bytes</span></span>|<span data-ttu-id="f3c70-112">ASCII 数据</span><span class="sxs-lookup"><span data-stu-id="f3c70-112">ASCII data</span></span>|
|:-----|:-----|:-----|
| `0000000000` <br/> | `03 01 01 00 00 00 45 00 00 00 08 00 00 00 00 00` <br/> | `???...E...?.....` <br/> |
| `0000000010` <br/> | `0A 00 54 00 65 00 78 00 74 00 46 00 69 00 65 00` <br/> | `?.T.e.x.t.F.i.e.` <br/> |
| `0000000020` <br/> | `6C 00 64 00 31 00 0A 54 65 78 74 46 69 65 6C 64` <br/> | `l.d.1.?TextField` <br/> |
| `0000000030` <br/> | `31 00 00 00 00 00 00 00 00 15 00 00 00 0A 54 00` <br/> | `1........?...?T.` <br/> |
| `0000000040` <br/> | `65 00 78 00 74 00 46 00 69 00 65 00 6C 00 64 00` <br/> | `e.x.t.F.i.e.l.d.` <br/> |
| `0000000050` <br/> | `31 00 00 00 00 00` <br/> | `1.....` <br/> |
   
<span data-ttu-id="f3c70-113">下面是 PropertyDefinition 流的示例数据的分析：</span><span class="sxs-lookup"><span data-stu-id="f3c70-113">The following is a parse of the sample data for the PropertyDefinition stream:</span></span>
  
- <span data-ttu-id="f3c70-114">版本：Offset 0x0，2 个字节：0x0103 (PropDefV2) 。</span><span class="sxs-lookup"><span data-stu-id="f3c70-114">Version: Offset 0x0, 2 bytes: 0x0103 (PropDefV2).</span></span>
    
- <span data-ttu-id="f3c70-115">FieldDefinitionCount：偏移0x2，4 个字节：0x1 (1) 。</span><span class="sxs-lookup"><span data-stu-id="f3c70-115">FieldDefinitionCount: Offset 0x2, 4 bytes: 0x1 (1).</span></span>
    
- <span data-ttu-id="f3c70-116">FieldDefinitions：Offset 0x6，1 个 FieldDefinition 流的数组。</span><span class="sxs-lookup"><span data-stu-id="f3c70-116">FieldDefinitions: Offset 0x6, array of 1 FieldDefinition stream.</span></span>
    
  - <span data-ttu-id="f3c70-117">标志：Offset 0x6，4 字节：0x45 (PDO_IS_CUSTOM|PDO_PRINT_SAVEAS|PDO_PRINT_SAVEAS_DEF) 。</span><span class="sxs-lookup"><span data-stu-id="f3c70-117">Flags: Offset 0x6, 4 bytes: 0x45 (PDO_IS_CUSTOM|PDO_PRINT_SAVEAS|PDO_PRINT_SAVEAS_DEF).</span></span>
    
  - <span data-ttu-id="f3c70-118">VT：偏移0xA，2 个字节 **：0x8 (VT_BSTR) 。**</span><span class="sxs-lookup"><span data-stu-id="f3c70-118">VT: Offset 0xA, 2 bytes: 0x8 (**VT_BSTR**).</span></span>
    
  - <span data-ttu-id="f3c70-119">DispId：偏移0xC，4 个字节：0x0 (0) 。</span><span class="sxs-lookup"><span data-stu-id="f3c70-119">DispId: Offset 0xC, 4 bytes: 0x0 (0).</span></span>
    
  - <span data-ttu-id="f3c70-120">NmidNameLength：偏移0x10，2 个字节：0xA (10) 。</span><span class="sxs-lookup"><span data-stu-id="f3c70-120">NmidNameLength: Offset 0x10, 2 bytes: 0xA (10).</span></span>
    
  - <span data-ttu-id="f3c70-121">NmidName：Offset 0x12，10 个 WCHAR 的数组。</span><span class="sxs-lookup"><span data-stu-id="f3c70-121">NmidName: Offset 0x12, array of 10 WCHARs.</span></span> <span data-ttu-id="f3c70-122">Unicode 字符串值："TextField1"。</span><span class="sxs-lookup"><span data-stu-id="f3c70-122">Unicode string value: "TextField1".</span></span>
    
  - <span data-ttu-id="f3c70-123">NameANSI：Offset 0x26、PackedAnsiString 流。</span><span class="sxs-lookup"><span data-stu-id="f3c70-123">NameANSI: Offset 0x26, PackedAnsiString stream.</span></span>
    
    - <span data-ttu-id="f3c70-124">长度：偏移0x26，1 字节：0xA (10) 。</span><span class="sxs-lookup"><span data-stu-id="f3c70-124">Length: Offset 0x26, 1 byte: 0xA (10).</span></span>
      
    - <span data-ttu-id="f3c70-125">字符：Offset 0x27，10 个 CHA 的数组。</span><span class="sxs-lookup"><span data-stu-id="f3c70-125">Characters: Offset 0x27, array of 10 CHARs.</span></span> <span data-ttu-id="f3c70-126">ANSI 字符串值："TextField1"。</span><span class="sxs-lookup"><span data-stu-id="f3c70-126">ANSI string value: "TextField1".</span></span>
    
  - <span data-ttu-id="f3c70-127">FormulaANSI：Offset 0x31、PackedAnsiString 流。</span><span class="sxs-lookup"><span data-stu-id="f3c70-127">FormulaANSI: Offset 0x31, PackedAnsiString stream.</span></span>
    
    - <span data-ttu-id="f3c70-128">长度：偏移0x31，1 字节：0x0 (0) 。</span><span class="sxs-lookup"><span data-stu-id="f3c70-128">Length: Offset 0x31, 1 byte: 0x0 (0).</span></span>
      
    - <span data-ttu-id="f3c70-129">字符：Offset 0x32，0 个 CHA 的数组。</span><span class="sxs-lookup"><span data-stu-id="f3c70-129">Characters: Offset 0x32, array of 0 CHARs.</span></span> <span data-ttu-id="f3c70-130">空 ANSI 字符串。</span><span class="sxs-lookup"><span data-stu-id="f3c70-130">Empty ANSI string.</span></span>
    
  - <span data-ttu-id="f3c70-131">ValidationRuleANSI：Offset 0x32、PackedAnsiString 流。</span><span class="sxs-lookup"><span data-stu-id="f3c70-131">ValidationRuleANSI: Offset 0x32, PackedAnsiString stream.</span></span>
    
    - <span data-ttu-id="f3c70-132">长度：偏移0x32，1 字节：0x0 (0) 。</span><span class="sxs-lookup"><span data-stu-id="f3c70-132">Length: Offset 0x32, 1 byte: 0x0 (0).</span></span>
      
    - <span data-ttu-id="f3c70-133">字符：Offset 0x33，0 个 CHA 的数组。</span><span class="sxs-lookup"><span data-stu-id="f3c70-133">Characters: Offset 0x33, array of 0 CHARs.</span></span> <span data-ttu-id="f3c70-134">空 ANSI 字符串。</span><span class="sxs-lookup"><span data-stu-id="f3c70-134">Empty ANSI string.</span></span>
    
  - <span data-ttu-id="f3c70-135">ValidationTextANSI：Offset 0x33、PackedAnsiString 流。</span><span class="sxs-lookup"><span data-stu-id="f3c70-135">ValidationTextANSI: Offset 0x33, PackedAnsiString stream.</span></span>
    
    - <span data-ttu-id="f3c70-136">长度：偏移0x33，1 字节：0x0 (0) 。</span><span class="sxs-lookup"><span data-stu-id="f3c70-136">Length: Offset 0x33, 1 byte: 0x0 (0).</span></span>
      
    - <span data-ttu-id="f3c70-137">字符：Offset 0x34，0 个 CHA 的数组。</span><span class="sxs-lookup"><span data-stu-id="f3c70-137">Characters: Offset 0x34, array of 0 CHARs.</span></span> <span data-ttu-id="f3c70-138">空 ANSI 字符串。</span><span class="sxs-lookup"><span data-stu-id="f3c70-138">Empty ANSI string.</span></span>
    
  - <span data-ttu-id="f3c70-139">ErrorANSI：Offset 0x34、PackedAnsiString 流。</span><span class="sxs-lookup"><span data-stu-id="f3c70-139">ErrorANSI: Offset 0x34, PackedAnsiString stream.</span></span>
    
    - <span data-ttu-id="f3c70-140">长度：偏移0x34，1 字节：0x0 (0) 。</span><span class="sxs-lookup"><span data-stu-id="f3c70-140">Length: Offset 0x34, 1 byte: 0x0 (0).</span></span>
      
    - <span data-ttu-id="f3c70-141">字符：Offset 0x35，0 个 CHA 的数组。</span><span class="sxs-lookup"><span data-stu-id="f3c70-141">Characters: Offset 0x35, array of 0 CHARs.</span></span> <span data-ttu-id="f3c70-142">空 ANSI 字符串。</span><span class="sxs-lookup"><span data-stu-id="f3c70-142">Empty ANSI string.</span></span>
    
  - <span data-ttu-id="f3c70-143">InternalType：Offset 0x35，4 个字节：0x0 (iTypeString) 。</span><span class="sxs-lookup"><span data-stu-id="f3c70-143">InternalType: Offset 0x35, 4 bytes: 0x0 (iTypeString).</span></span>
    
  - <span data-ttu-id="f3c70-144">SkipBlocks：Offset 0x39，一系列 SkipBlock 流。</span><span class="sxs-lookup"><span data-stu-id="f3c70-144">SkipBlocks: Offset 0x39, series of SkipBlock streams.</span></span>
    
  - <span data-ttu-id="f3c70-145">First SkipBlock</span><span class="sxs-lookup"><span data-stu-id="f3c70-145">First SkipBlock</span></span>
    
    - <span data-ttu-id="f3c70-146">大小：偏移0x39，4 个字节：0x15 (21) 。</span><span class="sxs-lookup"><span data-stu-id="f3c70-146">Size: Offset 0x39, 4 bytes: 0x15 (21).</span></span>
      
    - <span data-ttu-id="f3c70-147">Content：Offset 0x3D，21 字节数组。</span><span class="sxs-lookup"><span data-stu-id="f3c70-147">Content: Offset 0x3D, array of 21 bytes.</span></span> <span data-ttu-id="f3c70-148">这是第一个 SkipBlock 流，因此此数组包含 FirstSkipBlockContent 流。</span><span class="sxs-lookup"><span data-stu-id="f3c70-148">This is the first SkipBlock stream, so this array contains a FirstSkipBlockContent stream.</span></span>
      
      - <span data-ttu-id="f3c70-149">FieldName：Offset 0x3D、PackedUnicodeString 流。</span><span class="sxs-lookup"><span data-stu-id="f3c70-149">FieldName: Offset 0x3D, PackedUnicodeString stream.</span></span>
        
        - <span data-ttu-id="f3c70-150">长度：偏移0x3D，1 字节：0xA (10) 。</span><span class="sxs-lookup"><span data-stu-id="f3c70-150">Length: Offset 0x3D, 1 byte: 0xA (10).</span></span>
          
        - <span data-ttu-id="f3c70-151">字符：Offset 0x3E，10 个 WCHAR 数组。</span><span class="sxs-lookup"><span data-stu-id="f3c70-151">Characters: Offset 0x3E, array of 10 WCHARs.</span></span> <span data-ttu-id="f3c70-152">Unicode 字符串值："TextField1"。</span><span class="sxs-lookup"><span data-stu-id="f3c70-152">Unicode string value: "TextField1".</span></span>
    
  - <span data-ttu-id="f3c70-153">Second SkipBlock</span><span class="sxs-lookup"><span data-stu-id="f3c70-153">Second SkipBlock</span></span>
    
    - <span data-ttu-id="f3c70-154">大小：偏移0x52，4 个字节：0x0 (0) 。</span><span class="sxs-lookup"><span data-stu-id="f3c70-154">Size: Offset 0x52, 4 bytes: 0x0 (0).</span></span> <span data-ttu-id="f3c70-155">这是终止的 SkipBlock 流。</span><span class="sxs-lookup"><span data-stu-id="f3c70-155">This is the terminating SkipBlock stream.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f3c70-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3c70-156">See also</span></span>

- [<span data-ttu-id="f3c70-157">Outlook项目和字段</span><span class="sxs-lookup"><span data-stu-id="f3c70-157">Outlook Items and Fields</span></span>](outlook-items-and-fields.md)
- [<span data-ttu-id="f3c70-158">流结构</span><span class="sxs-lookup"><span data-stu-id="f3c70-158">Stream Structures</span></span>](stream-structures.md)
- [<span data-ttu-id="f3c70-159">PropertyDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="f3c70-159">PropertyDefinition Stream Structure</span></span>](propertydefinition-stream-structure.md)
- [<span data-ttu-id="f3c70-160">FieldDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="f3c70-160">FieldDefinition Stream Structure</span></span>](fielddefinition-stream-structure.md)
- [<span data-ttu-id="f3c70-161">SkipBlock 流结构</span><span class="sxs-lookup"><span data-stu-id="f3c70-161">SkipBlock Stream Structure</span></span>](skipblock-stream-structure.md)
- [<span data-ttu-id="f3c70-162">FirstSkipBlockContent 流结构</span><span class="sxs-lookup"><span data-stu-id="f3c70-162">FirstSkipBlockContent Stream Structure</span></span>](firstskipblockcontent-stream-structure.md)
- [<span data-ttu-id="f3c70-163">PackedAnsiString 流结构</span><span class="sxs-lookup"><span data-stu-id="f3c70-163">PackedAnsiString Stream Structure</span></span>](packedansistring-stream-structure.md)
- [<span data-ttu-id="f3c70-164">PackedUnicodeString 流结构</span><span class="sxs-lookup"><span data-stu-id="f3c70-164">PackedUnicodeString Stream Structure</span></span>](packedunicodestring-stream-structure.md)

