---
title: FolderUserFields 流示例
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 30e5e887-a324-4ed2-ba2a-eb4c19ba38d2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e5251a619c70221987847830897ba349d63fd9cb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433974"
---
# <a name="folderuserfields-stream-sample"></a><span data-ttu-id="b6d26-103">FolderUserFields 流示例</span><span class="sxs-lookup"><span data-stu-id="b6d26-103">FolderUserFields stream sample</span></span>

<span data-ttu-id="b6d26-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b6d26-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b6d26-105">本主题介绍 FolderUserFields 流的示例。</span><span class="sxs-lookup"><span data-stu-id="b6d26-105">This topic describes an example of a FolderUserFields stream.</span></span> <span data-ttu-id="b6d26-106">流包含用户定义的字段的定义  `TextField1` 。</span><span class="sxs-lookup"><span data-stu-id="b6d26-106">The stream contains a definition of a user-defined field,  `TextField1`.</span></span> <span data-ttu-id="b6d26-107">类型为 **Text**，FolderUserFields 流包含 FolderUserFieldsAnsi 和 FolderUserFieldsUnicode 部分。</span><span class="sxs-lookup"><span data-stu-id="b6d26-107">The type is **Text**, and the FolderUserFields stream contains both FolderUserFieldsAnsi and FolderUserFieldsUnicode parts.</span></span> <span data-ttu-id="b6d26-108">有关详细信息，请参阅 [Folder Fields Stream Structures](folder-fields-stream-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="b6d26-108">For more information see [Folder Fields Stream Structures](folder-fields-stream-structures.md).</span></span>
  
## <a name="data-dump"></a><span data-ttu-id="b6d26-109">数据转储</span><span class="sxs-lookup"><span data-stu-id="b6d26-109">Data dump</span></span>

<span data-ttu-id="b6d26-110">下面是流的数据转储，就像在二进制编辑器中显示一样。</span><span class="sxs-lookup"><span data-stu-id="b6d26-110">The following is a data dump of the stream as it would be displayed in a binary editor.</span></span>
  
|<span data-ttu-id="b6d26-111">流偏移</span><span class="sxs-lookup"><span data-stu-id="b6d26-111">Stream offset</span></span>|<span data-ttu-id="b6d26-112">数据字节数</span><span class="sxs-lookup"><span data-stu-id="b6d26-112">Data bytes</span></span>|<span data-ttu-id="b6d26-113">ASCII 数据</span><span class="sxs-lookup"><span data-stu-id="b6d26-113">ASCII data</span></span>|
|:-----|:-----|:-----|
| `0000000000` <br/> | `02 00 00 00 01 00 00 00 0A 00 54 65 78 74 46 69` <br/> | `..........TextFi` <br/> |
| `0000000010` <br/> | `65 6C 64 31 29 03 02 00 00 00 00 00 C0 00 00 00` <br/> | `eld1).......A...` <br/> |
| `0000000020` <br/> | `00 00 00 46 07 00 00 80 00 00 00 00 00 00 00 00` <br/> | `...F............` <br/> |
| `0000000030` <br/> | `00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00` <br/> | `................` <br/> |
| `0000000040` <br/> | `00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00` <br/> | `................` <br/> |
| `0000000050` <br/> | `00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00` <br/> | `................` <br/> |
| `0000000060` <br/> | `00 00 00 00 00 00 02 00 00 00 01 00 00 00 0A 00` <br/> | `................` <br/> |
| `0000000070` <br/> | `54 00 65 00 78 00 74 00 46 00 69 00 65 00 6C 00` <br/> | `T.e.x.t.F.i.e.l.` <br/> |
| `0000000080` <br/> | `64 00 31 00 29 03 02 00 00 00 00 00 C0 00 00 00` <br/> | `d.1.).......A...` <br/> |
| `0000000090` <br/> | `00 00 00 46 07 00 00 80 00 00 00 00 00 00 00 00` <br/> | `...F............` <br/> |
| `00000000A0` <br/> | `00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00` <br/> | `................` <br/> |
| `00000000B0` <br/> | `00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00` <br/> | `................` <br/> |
| `00000000C0` <br/> | `00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00` <br/> | `................` <br/> |
| `00000000D0` <br/> | `00 00 00 00 00 00` <br/> | `......` <br/> |
   

<span data-ttu-id="b6d26-114">以下是 **FolderUserFields** 流的示例数据分析：</span><span class="sxs-lookup"><span data-stu-id="b6d26-114">The following is a parse of the sample data for the **FolderUserFields** stream:</span></span>
  
- <span data-ttu-id="b6d26-115">FolderUserFieldsAnsi：Offset 0x0。</span><span class="sxs-lookup"><span data-stu-id="b6d26-115">FolderUserFieldsAnsi: Offset 0x0.</span></span>
    
  - <span data-ttu-id="b6d26-116">FieldDefinitionCount：Offset 0x0，4 个字节：0x00000002 (2) 。</span><span class="sxs-lookup"><span data-stu-id="b6d26-116">FieldDefinitionCount: Offset 0x0, 4 bytes: 0x00000002 (2).</span></span>
    
  - <span data-ttu-id="b6d26-117">FieldDefinitions：Offset 0x4，2 个 FolderFieldDefinitionA 流的数组。</span><span class="sxs-lookup"><span data-stu-id="b6d26-117">FieldDefinitions: Offset 0x4, array of 2 FolderFieldDefinitionA streams.</span></span>
    
    <span data-ttu-id="b6d26-118">**第一个数组元素**：</span><span class="sxs-lookup"><span data-stu-id="b6d26-118">**First array element**:</span></span>
    
    - <span data-ttu-id="b6d26-119">FieldType：Offset 0x4，4 个字节：0x00000001 (ftString) 。</span><span class="sxs-lookup"><span data-stu-id="b6d26-119">FieldType: Offset 0x4, 4 bytes: 0x00000001 (ftString).</span></span>
      
    - <span data-ttu-id="b6d26-120">FieldNameLength：Offset 0x8，2 个字节：0x000A (10) </span><span class="sxs-lookup"><span data-stu-id="b6d26-120">FieldNameLength: Offset 0x8, 2 bytes: 0x000A (10)</span></span>
      
    - <span data-ttu-id="b6d26-121">FieldName：Offset 0xA，10 个 CHA 的数组。</span><span class="sxs-lookup"><span data-stu-id="b6d26-121">FieldName: Offset 0xA, array of 10 CHARs.</span></span> <span data-ttu-id="b6d26-122">ANSI 字符串值："TextField1"。</span><span class="sxs-lookup"><span data-stu-id="b6d26-122">ANSI string value: "TextField1".</span></span>
      
    - <span data-ttu-id="b6d26-123">常见：偏移0x14。</span><span class="sxs-lookup"><span data-stu-id="b6d26-123">Common: Offset 0x14.</span></span>
    
      - <span data-ttu-id="b6d26-124">PropSetGuid：Offset 0x14，16 个字节：{00020329-0000-0000-C000-0000000000046} (PS_PUBLIC_STRINGS) 。</span><span class="sxs-lookup"><span data-stu-id="b6d26-124">PropSetGuid: Offset 0x14, 16 bytes: {00020329-0000-0000-C000-000000000046} (PS_PUBLIC_STRINGS).</span></span>
        
      - <span data-ttu-id="b6d26-125">fcapm：Offset 0x24，4 个字节：0x80000007 (FCAPM_CAN_EDIT|FCAPM_CAN_SORT|FCAPM_CAN_GROUP|FCAPM_CAN_EDIT_IN_ITEM) 。</span><span class="sxs-lookup"><span data-stu-id="b6d26-125">fcapm: Offset 0x24, 4 bytes: 0x80000007 (FCAPM_CAN_EDIT| FCAPM_CAN_SORT| FCAPM_CAN_GROUP|FCAPM_CAN_EDIT_IN_ITEM).</span></span>
        
      - <span data-ttu-id="b6d26-126">dwString：Offset 0x28，4 个字节：0x00000000。</span><span class="sxs-lookup"><span data-stu-id="b6d26-126">dwString: Offset 0x28, 4 bytes: 0x00000000.</span></span>
        
      - <span data-ttu-id="b6d26-127">dwBitmap：偏移0x2C，4 个字节：0x00000000。</span><span class="sxs-lookup"><span data-stu-id="b6d26-127">dwBitmap: Offset 0x2C, 4 bytes: 0x00000000.</span></span>
        
      - <span data-ttu-id="b6d26-128">dwDisplay： Offset 0x30， 4 bytes： 0x00000000.</span><span class="sxs-lookup"><span data-stu-id="b6d26-128">dwDisplay: Offset 0x30, 4 bytes: 0x00000000.</span></span>
        
      - <span data-ttu-id="b6d26-129">iFmt：偏移0x34，4 个字节：0x00000000。</span><span class="sxs-lookup"><span data-stu-id="b6d26-129">iFmt: Offset 0x34, 4 bytes: 0x00000000.</span></span>
        
      - <span data-ttu-id="b6d26-130">wszFormulaLength：Offset 0x38，2 个字节：0x0000 (0) 。</span><span class="sxs-lookup"><span data-stu-id="b6d26-130">wszFormulaLength: Offset 0x38, 2 bytes: 0x0000 (0).</span></span>
        
      - <span data-ttu-id="b6d26-131">wszFormula：Offset 0x3A，0 个 WCHAR 数组。</span><span class="sxs-lookup"><span data-stu-id="b6d26-131">wszFormula: Offset 0x3A, array of 0 WCHARs.</span></span> <span data-ttu-id="b6d26-132">空字符串值。</span><span class="sxs-lookup"><span data-stu-id="b6d26-132">Empty string value.</span></span>
    
    <span data-ttu-id="b6d26-133">**第二个数组元素**：</span><span class="sxs-lookup"><span data-stu-id="b6d26-133">**Second array element**:</span></span>
    
    - <span data-ttu-id="b6d26-134">FieldType：Offset 0x3A，4 个字节：0x00000000 (ftNone) 。</span><span class="sxs-lookup"><span data-stu-id="b6d26-134">FieldType: Offset 0x3A, 4 bytes: 0x00000000 (ftNone).</span></span>
      
    - <span data-ttu-id="b6d26-135">FieldNameLength：Offset 0x3E，2 个字节：0x0000 (0) 。</span><span class="sxs-lookup"><span data-stu-id="b6d26-135">FieldNameLength: Offset 0x3E, 2 bytes: 0x0000 (0).</span></span>
      
    - <span data-ttu-id="b6d26-136">FieldName：Offset 0x40，0 个 CHA 的数组。</span><span class="sxs-lookup"><span data-stu-id="b6d26-136">FieldName: Offset 0x40, array of 0 CHARs.</span></span> <span data-ttu-id="b6d26-137">空字符串值。</span><span class="sxs-lookup"><span data-stu-id="b6d26-137">Empty string value.</span></span>
      
    - <span data-ttu-id="b6d26-138">常见：偏移0x40。</span><span class="sxs-lookup"><span data-stu-id="b6d26-138">Common: Offset 0x40.</span></span>
    
      - <span data-ttu-id="b6d26-139">PropSetGuid：偏移0x40，16 个字节 {00000000-0000-0000-0000-000000000000} ： (GUID_NULL) 。</span><span class="sxs-lookup"><span data-stu-id="b6d26-139">PropSetGuid: Offset 0x40, 16 bytes: {00000000-0000-0000-0000-000000000000} (GUID_NULL).</span></span>
        
      - <span data-ttu-id="b6d26-140">fcapm：Offset 0x50，4 个字节：0x00000000 (0) 。</span><span class="sxs-lookup"><span data-stu-id="b6d26-140">fcapm: Offset 0x50, 4 bytes: 0x00000000 (0).</span></span>
        
      - <span data-ttu-id="b6d26-141">dwString：Offset 0x54，4 个字节：0x00000000。</span><span class="sxs-lookup"><span data-stu-id="b6d26-141">dwString: Offset 0x54, 4 bytes: 0x00000000.</span></span>
        
      - <span data-ttu-id="b6d26-142">dwBitmap：偏移0x58，4 个字节：0x00000000。</span><span class="sxs-lookup"><span data-stu-id="b6d26-142">dwBitmap: Offset 0x58, 4 bytes: 0x00000000.</span></span>
        
      - <span data-ttu-id="b6d26-143">dwDisplay：Offset 0x5C，4 个字节：0x00000000。</span><span class="sxs-lookup"><span data-stu-id="b6d26-143">dwDisplay: Offset 0x5C, 4 bytes: 0x00000000.</span></span>
        
      - <span data-ttu-id="b6d26-144">iFmt：偏移0x60，4 个字节：0x00000000。</span><span class="sxs-lookup"><span data-stu-id="b6d26-144">iFmt: Offset 0x60, 4 bytes: 0x00000000.</span></span>
        
      - <span data-ttu-id="b6d26-145">wszFormulaLength：偏移量 0x64，2 字节：0x0000 (0) 。</span><span class="sxs-lookup"><span data-stu-id="b6d26-145">wszFormulaLength: Offset 0x64, 2 bytes: 0x0000 (0).</span></span>
        
      - <span data-ttu-id="b6d26-146">wszFormula：Offset 0x66，0 个 WCHAR 数组。</span><span class="sxs-lookup"><span data-stu-id="b6d26-146">wszFormula: Offset 0x66, array of 0 WCHARs.</span></span> <span data-ttu-id="b6d26-147">空字符串值。</span><span class="sxs-lookup"><span data-stu-id="b6d26-147">Empty string value.</span></span>
    
- <span data-ttu-id="b6d26-148">FolderUserFieldsUnicode：Offset 0x66。</span><span class="sxs-lookup"><span data-stu-id="b6d26-148">FolderUserFieldsUnicode: Offset 0x66.</span></span>
    
  - <span data-ttu-id="b6d26-149">FieldDefinitionCount：Offset 0x66，4 个字节：0x00000002 (2) 。</span><span class="sxs-lookup"><span data-stu-id="b6d26-149">FieldDefinitionCount: Offset 0x66, 4 bytes: 0x00000002 (2).</span></span>
    
  - <span data-ttu-id="b6d26-150">FieldDefinitions：Offset 0x6A，2 个 FolderFieldDefinitionW 流的数组。</span><span class="sxs-lookup"><span data-stu-id="b6d26-150">FieldDefinitions: Offset 0x6A, array of 2 FolderFieldDefinitionW streams.</span></span>
    
    <span data-ttu-id="b6d26-151">**第一个数组元素**：</span><span class="sxs-lookup"><span data-stu-id="b6d26-151">**First array element**:</span></span>
    
    - <span data-ttu-id="b6d26-152">FieldType：Offset 0x6A，4 个字节：0x00000001 (ftString) 。</span><span class="sxs-lookup"><span data-stu-id="b6d26-152">FieldType: Offset 0x6A, 4 bytes: 0x00000001 (ftString).</span></span>
      
    - <span data-ttu-id="b6d26-153">FieldNameLength：Offset 0x6E，2 个字节：0x000A (10) 。</span><span class="sxs-lookup"><span data-stu-id="b6d26-153">FieldNameLength: Offset 0x6E, 2 bytes: 0x000A (10).</span></span>
      
    - <span data-ttu-id="b6d26-154">FieldName：Offset 0x70，10 个 WCHAR 数组。</span><span class="sxs-lookup"><span data-stu-id="b6d26-154">FieldName: Offset 0x70, array of 10 WCHARs.</span></span> <span data-ttu-id="b6d26-155">Unicode 字符串值："TextField1"。</span><span class="sxs-lookup"><span data-stu-id="b6d26-155">Unicode string value: "TextField1".</span></span>
      
    - <span data-ttu-id="b6d26-156">常见：偏移0x84。</span><span class="sxs-lookup"><span data-stu-id="b6d26-156">Common: Offset 0x84.</span></span>
    
      - <span data-ttu-id="b6d26-157">PropSetGuid：Offset 0x84，16 个字节：{00020329-0000-0000-C000-0000000000046} (PS_PUBLIC_STRINGS) 。</span><span class="sxs-lookup"><span data-stu-id="b6d26-157">PropSetGuid: Offset 0x84, 16 bytes: {00020329-0000-0000-C000-000000000046} (PS_PUBLIC_STRINGS).</span></span>
        
      - <span data-ttu-id="b6d26-158">fcapm：Offset 0x94，4 个字节：0x80000007 (FCAPM_CAN_EDIT|FCAPM_CAN_SORT|FCAPM_CAN_GROUP|FCAPM_CAN_EDIT_IN_ITEM) 。</span><span class="sxs-lookup"><span data-stu-id="b6d26-158">fcapm: Offset 0x94, 4 bytes: 0x80000007 (FCAPM_CAN_EDIT| FCAPM_CAN_SORT| FCAPM_CAN_GROUP|FCAPM_CAN_EDIT_IN_ITEM).</span></span>
        
      - <span data-ttu-id="b6d26-159">dwString：Offset 0x98，4 个字节：0x00000000。</span><span class="sxs-lookup"><span data-stu-id="b6d26-159">dwString: Offset 0x98, 4 bytes: 0x00000000.</span></span>
        
      - <span data-ttu-id="b6d26-160">dwBitmap：偏移0x9C，4 个字节：0x00000000。</span><span class="sxs-lookup"><span data-stu-id="b6d26-160">dwBitmap: Offset 0x9C, 4 bytes: 0x00000000.</span></span>
        
      - <span data-ttu-id="b6d26-161">dwDisplay： Offset 0xA0， 4 bytes： 0x00000000.</span><span class="sxs-lookup"><span data-stu-id="b6d26-161">dwDisplay: Offset 0xA0, 4 bytes: 0x00000000.</span></span>
        
      - <span data-ttu-id="b6d26-162">iFmt：偏移0xA4，4 个字节：0x00000000。</span><span class="sxs-lookup"><span data-stu-id="b6d26-162">iFmt: Offset 0xA4, 4 bytes: 0x00000000.</span></span>
        
      - <span data-ttu-id="b6d26-163">wszFormulaLength：偏移量 0xA8，2 字节：0x0000 (0) 。</span><span class="sxs-lookup"><span data-stu-id="b6d26-163">wszFormulaLength: Offset 0xA8, 2 bytes: 0x0000 (0).</span></span>
        
      - <span data-ttu-id="b6d26-164">wszFormula：Offset 0xAA，0 个 WCHAR 数组。</span><span class="sxs-lookup"><span data-stu-id="b6d26-164">wszFormula: Offset 0xAA, array of 0 WCHARs.</span></span> <span data-ttu-id="b6d26-165">空字符串值。</span><span class="sxs-lookup"><span data-stu-id="b6d26-165">Empty string value.</span></span>
    
    <span data-ttu-id="b6d26-166">**第二个数组元素**：</span><span class="sxs-lookup"><span data-stu-id="b6d26-166">**Second array element**:</span></span>
    
    - <span data-ttu-id="b6d26-167">FieldType：Offset 0xAA，4 个字节：0x00000000 (ftNone) 。</span><span class="sxs-lookup"><span data-stu-id="b6d26-167">FieldType: Offset 0xAA, 4 bytes: 0x00000000 (ftNone).</span></span>
      
    - <span data-ttu-id="b6d26-168">FieldNameLength： Offset 0xAE， 2 bytes： 0x0000 (0) .</span><span class="sxs-lookup"><span data-stu-id="b6d26-168">FieldNameLength: Offset 0xAE, 2 bytes: 0x0000 (0).</span></span>
      
    - <span data-ttu-id="b6d26-169">FieldName：Offset 0xB0，数组为 0 WCHAR。</span><span class="sxs-lookup"><span data-stu-id="b6d26-169">FieldName: Offset 0xB0, array of 0 WCHARs.</span></span> <span data-ttu-id="b6d26-170">空字符串值。</span><span class="sxs-lookup"><span data-stu-id="b6d26-170">Empty string value.</span></span>
      
    - <span data-ttu-id="b6d26-171">常见：偏移0xB0。</span><span class="sxs-lookup"><span data-stu-id="b6d26-171">Common: Offset 0xB0.</span></span>
    
      - <span data-ttu-id="b6d26-172">PropSetGuid：偏移0xB0，16 个字节 {00000000-0000-0000-0000-000000000000} ： (GUID_NULL) 。</span><span class="sxs-lookup"><span data-stu-id="b6d26-172">PropSetGuid: Offset 0xB0, 16 bytes: {00000000-0000-0000-0000-000000000000} (GUID_NULL).</span></span>
        
      - <span data-ttu-id="b6d26-173">fcapm：Offset 0xC0，4 个字节：0x00000000 (0) 。</span><span class="sxs-lookup"><span data-stu-id="b6d26-173">fcapm: Offset 0xC0, 4 bytes: 0x00000000 (0).</span></span>
        
      - <span data-ttu-id="b6d26-174">dwString：Offset 0xC4，4 个字节：0x00000000。</span><span class="sxs-lookup"><span data-stu-id="b6d26-174">dwString: Offset 0xC4, 4 bytes: 0x00000000.</span></span>
        
      - <span data-ttu-id="b6d26-175">dwBitmap：偏移0xC8，4 个字节：0x00000000。</span><span class="sxs-lookup"><span data-stu-id="b6d26-175">dwBitmap: Offset 0xC8, 4 bytes: 0x00000000.</span></span>
        
      - <span data-ttu-id="b6d26-176">dwDisplay： Offset 0xCC， 4 bytes： 0x00000000.</span><span class="sxs-lookup"><span data-stu-id="b6d26-176">dwDisplay: Offset 0xCC, 4 bytes: 0x00000000.</span></span>
        
      - <span data-ttu-id="b6d26-177">iFmt：偏移0xD0，4 个字节：0x00000000。</span><span class="sxs-lookup"><span data-stu-id="b6d26-177">iFmt: Offset 0xD0, 4 bytes: 0x00000000.</span></span>
        
      - <span data-ttu-id="b6d26-178">wszFormulaLength：偏移量 0xD4，2 字节：0x0000 (0) 。</span><span class="sxs-lookup"><span data-stu-id="b6d26-178">wszFormulaLength: Offset 0xD4, 2 bytes: 0x0000 (0).</span></span>
        
      - <span data-ttu-id="b6d26-179">wszFormula：Offset 0xD6，0 个 WCHAR 数组。</span><span class="sxs-lookup"><span data-stu-id="b6d26-179">wszFormula: Offset 0xD6, array of 0 WCHARs.</span></span> <span data-ttu-id="b6d26-180">空字符串值。</span><span class="sxs-lookup"><span data-stu-id="b6d26-180">Empty string value.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b6d26-181">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6d26-181">See also</span></span>

- [<span data-ttu-id="b6d26-182">Outlook项目和字段</span><span class="sxs-lookup"><span data-stu-id="b6d26-182">Outlook Items and Fields</span></span>](outlook-items-and-fields.md)
- [<span data-ttu-id="b6d26-183">PropertyDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="b6d26-183">PropertyDefinition Stream Structure</span></span>](propertydefinition-stream-structure.md)
- [<span data-ttu-id="b6d26-184">FieldDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="b6d26-184">FieldDefinition Stream Structure</span></span>](fielddefinition-stream-structure.md)
- [<span data-ttu-id="b6d26-185">SkipBlock 流结构</span><span class="sxs-lookup"><span data-stu-id="b6d26-185">SkipBlock Stream Structure</span></span>](skipblock-stream-structure.md)
- [<span data-ttu-id="b6d26-186">FirstSkipBlockContent 流结构</span><span class="sxs-lookup"><span data-stu-id="b6d26-186">FirstSkipBlockContent Stream Structure</span></span>](firstskipblockcontent-stream-structure.md)
- [<span data-ttu-id="b6d26-187">PackedAnsiString 流结构</span><span class="sxs-lookup"><span data-stu-id="b6d26-187">PackedAnsiString Stream Structure</span></span>](packedansistring-stream-structure.md)
- [<span data-ttu-id="b6d26-188">PackedUnicodeString 流结构</span><span class="sxs-lookup"><span data-stu-id="b6d26-188">PackedUnicodeString Stream Structure</span></span>](packedunicodestring-stream-structure.md)

