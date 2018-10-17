---
title: 文件夹字段流结构
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: edbc9e6c-008c-4c13-9a0c-cb47ac0f3686
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 96051bd2b62fd7c0e908a1018aac0225e44986be
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385086"
---
# <a name="folder-fields-stream-structures"></a><span data-ttu-id="518a7-103">文件夹字段流结构</span><span class="sxs-lookup"><span data-stu-id="518a7-103">Folder Fields Stream Structures</span></span>

<span data-ttu-id="518a7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="518a7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="518a7-105">消息的[PidTagUserFields](pidtaguserfields-canonical-property.md)属性包含二进制数据流，FolderUserFields，其中包含的文件夹的用户定义的字段定义。</span><span class="sxs-lookup"><span data-stu-id="518a7-105">A message's [PidTagUserFields](pidtaguserfields-canonical-property.md) property contains a binary stream, FolderUserFields, which contains the folder user-defined field definitions.</span></span> <span data-ttu-id="518a7-106">本主题描述有关用户定义的字段定义的文件夹的流结构。</span><span class="sxs-lookup"><span data-stu-id="518a7-106">This topic describes the stream structures for folder user-defined field definitions.</span></span> 

<span data-ttu-id="518a7-107">FolderUserFields 流结构组成 FolderUserFieldsA 结构或 FolderUserFieldsA 结构跟 FolderUserFieldsW 结构。</span><span class="sxs-lookup"><span data-stu-id="518a7-107">A FolderUserFields stream structure consists of either a FolderUserFieldsA structure or a FolderUserFieldsA structure followed by a FolderUserFieldsW structure.</span></span>
  
<span data-ttu-id="518a7-108">此流中的数据元素存储紧随每个其他指定顺序如下：</span><span class="sxs-lookup"><span data-stu-id="518a7-108">Data elements in this stream are stored immediately following each other in the following specified order:</span></span>
  
- <span data-ttu-id="518a7-109">**FolderUserFieldsAnsi**: FolderUserFieldsA stream 结构。</span><span class="sxs-lookup"><span data-stu-id="518a7-109">**FolderUserFieldsAnsi**: A FolderUserFieldsA stream structure.</span></span>
    
- <span data-ttu-id="518a7-110">**FolderUserFieldsUnicode**（可选）： FolderUserFieldsW stream 结构。</span><span class="sxs-lookup"><span data-stu-id="518a7-110">**FolderUserFieldsUnicode** (optional): A FolderUserFieldsW stream structure.</span></span>
    
<span data-ttu-id="518a7-111">FolderUserFieldsUnicode 状态检测到的 FolderUserFieldsAnsi 长度大于 FolderUserFields 的总长度。</span><span class="sxs-lookup"><span data-stu-id="518a7-111">The presence of FolderUserFieldsUnicode is detected by the total length of the FolderUserFields being greater than the length of FolderUserFieldsAnsi.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="518a7-112">FolderUserFieldsAnsi 用于与旧，非 Unicode，版本的 MAPI 客户端的兼容性因此 FolderUserFieldsUnicode 是否存在，则忽略 FolderUserFieldsAnsi 的内容。</span><span class="sxs-lookup"><span data-stu-id="518a7-112">FolderUserFieldsAnsi is used for compatibility with older, non-Unicode, versions of MAPI clients, therefore if FolderUserFieldsUnicode is present, the contents of FolderUserFieldsAnsi is ignored.</span></span> <span data-ttu-id="518a7-113">若要避免可能的数据中 ANSI 转换，始终创建 FolderUserFields 流时丢失包含 FolderUserFieldsW 部件。</span><span class="sxs-lookup"><span data-stu-id="518a7-113">To avoid possible data loss in ANSI conversion, when creating a FolderUserFields stream always include the FolderUserFieldsW part.</span></span> 
  
## <a name="folderuserfieldsa-stream-structure"></a><span data-ttu-id="518a7-114">FolderUserFieldsA 流结构</span><span class="sxs-lookup"><span data-stu-id="518a7-114">FolderUserFieldsA Stream Structure</span></span>

<span data-ttu-id="518a7-115">FolderUserFieldsA 流结构是数组 FolderFieldDefinitionA 流结构包含定义的用户定义的所有字段，在 Outlook 文件夹中，除非覆盖 FolderUserFields 结构的 FolderUserFieldsW 部分。</span><span class="sxs-lookup"><span data-stu-id="518a7-115">A FolderUserFieldsA stream structure is an array of FolderFieldDefinitionA stream structures that contain definitions for all user-defined fields in an Outlook folder, unless overridden by the FolderUserFieldsW part of the FolderUserFields structure.</span></span>
  
<span data-ttu-id="518a7-116">此流中的数据元素存储在-little-endian 字节的顺序，紧跟每个其他指定顺序如下：</span><span class="sxs-lookup"><span data-stu-id="518a7-116">Data elements in this stream are stored in little-endian byte order, immediately following each other in the following specified order:</span></span>
  
- <span data-ttu-id="518a7-117">**FieldDefinitionCount**: DWORD （4 个字节），此流中的字段定义的数目。</span><span class="sxs-lookup"><span data-stu-id="518a7-117">**FieldDefinitionCount**: DWORD (4 bytes), the number of field definitions in this stream.</span></span> <span data-ttu-id="518a7-118">这是**FieldDefinitions**数组中的元素的计数。</span><span class="sxs-lookup"><span data-stu-id="518a7-118">This is the count of elements in the **FieldDefinitions** array.</span></span>
    
- <span data-ttu-id="518a7-119">**FieldDefinitions**： 数组 FolderFieldDefinitionA stream 结构。</span><span class="sxs-lookup"><span data-stu-id="518a7-119">**FieldDefinitions**: An array of FolderFieldDefinitionA stream structures.</span></span> <span data-ttu-id="518a7-120">此数组的计数等于**FieldDefinitionCount**数据元素。</span><span class="sxs-lookup"><span data-stu-id="518a7-120">The count of this array is equal to the **FieldDefinitionCount** data element.</span></span>
    
<span data-ttu-id="518a7-121">除非此 FolderUserFieldsA 被覆盖的 FolderUserFieldsW 一部分 FolderUserFields 结构，该**FieldDefinitions**数组必须是"以 null 结尾"通过其最后一个 FolderFieldDefinitionA 元素 Common.FieldType 字段等于到 ftNull。</span><span class="sxs-lookup"><span data-stu-id="518a7-121">Unless this FolderUserFieldsA is overridden by the FolderUserFieldsW part of the FolderUserFields structure, the **FieldDefinitions** array must be "null-terminated" by having its last FolderFieldDefinitionA element's Common.FieldType field equal to ftNull.</span></span>
  
## <a name="folderuserfieldsw-stream-structure"></a><span data-ttu-id="518a7-122">FolderUserFieldsW 流结构</span><span class="sxs-lookup"><span data-stu-id="518a7-122">FolderUserFieldsW Stream Structure</span></span>

<span data-ttu-id="518a7-123">FolderUserFieldsW 流结构是 FolderFieldDefinitionW 流结构包含定义的 Outlook 文件夹中所有用户定义的字段的数组。</span><span class="sxs-lookup"><span data-stu-id="518a7-123">A FolderUserFieldsW stream structure is an array of FolderFieldDefinitionW stream structures that contain definitions for all user-defined fields in an Outlook folder.</span></span>
  
<span data-ttu-id="518a7-124">此流中的数据元素存储在-little-endian 字节的顺序，紧跟每个其他指定顺序如下：</span><span class="sxs-lookup"><span data-stu-id="518a7-124">Data elements in this stream are stored in little-endian byte order, immediately following each other in the following specified order:</span></span>
  
- <span data-ttu-id="518a7-125">**FieldDefinitionCount**: DWORD （4 个字节），此流中的字段定义的数目。</span><span class="sxs-lookup"><span data-stu-id="518a7-125">**FieldDefinitionCount**: DWORD (4 bytes), the number of field definitions in this stream.</span></span> <span data-ttu-id="518a7-126">这是**FieldDefinitions**数组中的元素的计数。</span><span class="sxs-lookup"><span data-stu-id="518a7-126">This is the count of elements in the **FieldDefinitions** array.</span></span>
    
- <span data-ttu-id="518a7-127">**FieldDefinitions**： 数组 FolderFieldDefinitionW stream 结构。</span><span class="sxs-lookup"><span data-stu-id="518a7-127">**FieldDefinitions**: An array of FolderFieldDefinitionW stream structures.</span></span> <span data-ttu-id="518a7-128">此数组的计数等于**FieldDefinitionCount**数据元素。</span><span class="sxs-lookup"><span data-stu-id="518a7-128">The count of this array is equal to the **FieldDefinitionCount** data element.</span></span>
    
<span data-ttu-id="518a7-129">**FieldDefinitions**数组必须是"以 null 结尾"，通过其最后一个 FolderFieldDefinitionW 元素 Common.FieldType 字段等于 ftNull。</span><span class="sxs-lookup"><span data-stu-id="518a7-129">The **FieldDefinitions** array must be "null-terminated" by having its last FolderFieldDefinitionW element's Common.FieldType field equal to ftNull.</span></span>
  
## <a name="folderfielddefinitiona-stream-structure"></a><span data-ttu-id="518a7-130">FolderFieldDefinitionA 流结构</span><span class="sxs-lookup"><span data-stu-id="518a7-130">FolderFieldDefinitionA Stream Structure</span></span>

<span data-ttu-id="518a7-131">FolderFieldDefinitionA 流结构与存储在 ANSI 中的字段名称中包含用户定义的字段的定义。</span><span class="sxs-lookup"><span data-stu-id="518a7-131">A FolderFieldDefinitionA stream structure contains a definition of a user-defined field with the field name stored in ANSI.</span></span>
  
<span data-ttu-id="518a7-132">此流中的数据元素存储在-little-endian 字节的顺序，紧跟每个其他指定顺序如下：</span><span class="sxs-lookup"><span data-stu-id="518a7-132">Data elements in this stream are stored in little-endian byte order, immediately following each other in the following specified order:</span></span>
  
- <span data-ttu-id="518a7-133">**FieldType**: FldType （4 个字节），此字段的类型。</span><span class="sxs-lookup"><span data-stu-id="518a7-133">**FieldType**: FldType (4 bytes), the type of this field.</span></span>
    
- <span data-ttu-id="518a7-134">**FieldNameLength**： 单词 （2 个字节）， **FieldName**数组中的元素的数目。</span><span class="sxs-lookup"><span data-stu-id="518a7-134">**FieldNameLength**: WORD (2 bytes), the number of elements in the **FieldName** array.</span></span>
    
- <span data-ttu-id="518a7-135">**FieldName**: CHAR 的数组。</span><span class="sxs-lookup"><span data-stu-id="518a7-135">**FieldName**: An array of CHAR.</span></span> <span data-ttu-id="518a7-136">这是 ANSI CP_ACP 代码页表示的字段名称。</span><span class="sxs-lookup"><span data-stu-id="518a7-136">This is the ANSI CP_ACP codepage representation of the field name.</span></span> <span data-ttu-id="518a7-137">此数组的计数等于**FieldNameLength**。</span><span class="sxs-lookup"><span data-stu-id="518a7-137">The count of this array is equal to **FieldNameLength**.</span></span> <span data-ttu-id="518a7-138">字段名称都必须满足的[UserProperties.Add](https://msdn.microsoft.com/library/microsoft.office.interop.outlook.userproperties.add.aspx)方法中指定的名称参数的限制。</span><span class="sxs-lookup"><span data-stu-id="518a7-138">The field name must satisfy the restrictions on the Name parameter as specified in the [UserProperties.Add](https://msdn.microsoft.com/library/microsoft.office.interop.outlook.userproperties.add.aspx) Method.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="518a7-139">出于旧的兼容性，Outlook 可能能够处理不满足这些限制某些**FieldName**值，但是这种情况下不包含的此主题。</span><span class="sxs-lookup"><span data-stu-id="518a7-139">For reasons of legacy compatibility, Outlook may be able to handle some **FieldName** values not satisfying these restrictions, however such cases are not covered by this topic.</span></span> 
  
- <span data-ttu-id="518a7-140">**常见**： FolderFieldDefinitionCommon stream 结构。</span><span class="sxs-lookup"><span data-stu-id="518a7-140">**Common**: A FolderFieldDefinitionCommon stream structure.</span></span>
    
## <a name="folderfielddefinitionw-stream-structure"></a><span data-ttu-id="518a7-141">FolderFieldDefinitionW 流结构</span><span class="sxs-lookup"><span data-stu-id="518a7-141">FolderFieldDefinitionW Stream Structure</span></span>

<span data-ttu-id="518a7-142">FolderFieldDefinitionW 流结构与存储在 Unicode 中的字段名称中包含用户定义的字段的定义。</span><span class="sxs-lookup"><span data-stu-id="518a7-142">A FolderFieldDefinitionW stream structure contains a definition of a user-defined field with the field name stored in Unicode.</span></span>
  
<span data-ttu-id="518a7-143">此流中的数据元素存储在-little-endian 字节的顺序，紧跟每个其他指定顺序如下：</span><span class="sxs-lookup"><span data-stu-id="518a7-143">Data elements in this stream are stored in little-endian byte order, immediately following each other in the following specified order:</span></span>
  
- <span data-ttu-id="518a7-144">**FieldType**: FldType （4 个字节），此字段的类型。</span><span class="sxs-lookup"><span data-stu-id="518a7-144">**FieldType**: FldType (4 bytes), the type of this field.</span></span>
    
- <span data-ttu-id="518a7-145">**FieldNameLength**： 单词 （2 个字节）， **FieldName**数组中的元素的数目。</span><span class="sxs-lookup"><span data-stu-id="518a7-145">**FieldNameLength**: WORD (2 bytes), the number of elements in the **FieldName** array.</span></span>
    
- <span data-ttu-id="518a7-146">**FieldName**: WCHAR 的数组。</span><span class="sxs-lookup"><span data-stu-id="518a7-146">**FieldName**: An array of WCHAR.</span></span> <span data-ttu-id="518a7-147">这是字段名称的 Unicode (utf-16) 表示形式。</span><span class="sxs-lookup"><span data-stu-id="518a7-147">This is the Unicode (UTF-16) representation of the field name.</span></span> <span data-ttu-id="518a7-148">此数组的计数等于**FieldNameLength**。</span><span class="sxs-lookup"><span data-stu-id="518a7-148">The count of this array is equal to **FieldNameLength**.</span></span> <span data-ttu-id="518a7-149">字段名称都必须满足的[UserProperties.Add](https://msdn.microsoft.com/library/microsoft.office.interop.outlook.userproperties.add.aspx)方法中指定的名称参数的限制。</span><span class="sxs-lookup"><span data-stu-id="518a7-149">The field name must satisfy the restrictions on the Name parameter as specified in the [UserProperties.Add](https://msdn.microsoft.com/library/microsoft.office.interop.outlook.userproperties.add.aspx) Method.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="518a7-150">出于旧的兼容性，Outlook 可能能够处理一些**FieldName**值不满足这些限制，但这种情况下不受本主题。</span><span class="sxs-lookup"><span data-stu-id="518a7-150">For reasons of legacy compatibility, Outlook may be able to handle some **FieldName** values not satisfying these restrictions, but such cases are not covered by this topic.</span></span> 
  
- <span data-ttu-id="518a7-151">**常见**： FolderFieldDefinitionCommon stream 结构。</span><span class="sxs-lookup"><span data-stu-id="518a7-151">**Common**: A FolderFieldDefinitionCommon stream structure.</span></span>
    
## <a name="fldtype-enumeration"></a><span data-ttu-id="518a7-152">FldType 枚举</span><span class="sxs-lookup"><span data-stu-id="518a7-152">FldType Enumeration</span></span>

<span data-ttu-id="518a7-153">下表列出了**FldType**枚举值。</span><span class="sxs-lookup"><span data-stu-id="518a7-153">**FldType** enumeration values are listed in the following table.</span></span> 
  
|<span data-ttu-id="518a7-154">名称</span><span class="sxs-lookup"><span data-stu-id="518a7-154">Name</span></span>|<span data-ttu-id="518a7-155">值</span><span class="sxs-lookup"><span data-stu-id="518a7-155">Value</span></span>|<span data-ttu-id="518a7-156">含义</span><span class="sxs-lookup"><span data-stu-id="518a7-156">Meaning</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="518a7-157">ftNull</span><span class="sxs-lookup"><span data-stu-id="518a7-157">ftNull</span></span>  <br/> |<span data-ttu-id="518a7-158">0x0</span><span class="sxs-lookup"><span data-stu-id="518a7-158">0x0</span></span>  <br/> |<span data-ttu-id="518a7-159">此字段类型用于 null 终止字段定义的数组。</span><span class="sxs-lookup"><span data-stu-id="518a7-159">This field type is used to null-terminate an array of field definitions.</span></span>  <br/> |
|<span data-ttu-id="518a7-160">ftString</span><span class="sxs-lookup"><span data-stu-id="518a7-160">ftString</span></span>  <br/> |<span data-ttu-id="518a7-161">0x1</span><span class="sxs-lookup"><span data-stu-id="518a7-161">0x1</span></span>  <br/> |<span data-ttu-id="518a7-162">文本</span><span class="sxs-lookup"><span data-stu-id="518a7-162">Text</span></span>  <br/> |
|<span data-ttu-id="518a7-163">ftInteger</span><span class="sxs-lookup"><span data-stu-id="518a7-163">ftInteger</span></span>  <br/> |<span data-ttu-id="518a7-164">0x3</span><span class="sxs-lookup"><span data-stu-id="518a7-164">0x3</span></span>  <br/> |<span data-ttu-id="518a7-165">整数</span><span class="sxs-lookup"><span data-stu-id="518a7-165">Integer</span></span>  <br/> |
|<span data-ttu-id="518a7-166">ftTime</span><span class="sxs-lookup"><span data-stu-id="518a7-166">ftTime</span></span>  <br/> |<span data-ttu-id="518a7-167">0x5</span><span class="sxs-lookup"><span data-stu-id="518a7-167">0x5</span></span>  <br/> |<span data-ttu-id="518a7-168">日期/时间</span><span class="sxs-lookup"><span data-stu-id="518a7-168">Date/Time</span></span>  <br/> |
|<span data-ttu-id="518a7-169">ftBoolean</span><span class="sxs-lookup"><span data-stu-id="518a7-169">ftBoolean</span></span>  <br/> |<span data-ttu-id="518a7-170">0x6</span><span class="sxs-lookup"><span data-stu-id="518a7-170">0x6</span></span>  <br/> |<span data-ttu-id="518a7-171">是/否</span><span class="sxs-lookup"><span data-stu-id="518a7-171">Yes/No</span></span>  <br/> |
|<span data-ttu-id="518a7-172">ftDuration</span><span class="sxs-lookup"><span data-stu-id="518a7-172">ftDuration</span></span>  <br/> |<span data-ttu-id="518a7-173">0x7</span><span class="sxs-lookup"><span data-stu-id="518a7-173">0x7</span></span>  <br/> |<span data-ttu-id="518a7-174">Duration</span><span class="sxs-lookup"><span data-stu-id="518a7-174">Duration</span></span>  <br/> |
|<span data-ttu-id="518a7-175">ftMultiString</span><span class="sxs-lookup"><span data-stu-id="518a7-175">ftMultiString</span></span>  <br/> |<span data-ttu-id="518a7-176">0xB</span><span class="sxs-lookup"><span data-stu-id="518a7-176">0xB</span></span>  <br/> |<span data-ttu-id="518a7-177">Keywords</span><span class="sxs-lookup"><span data-stu-id="518a7-177">Keywords</span></span>  <br/> |
|<span data-ttu-id="518a7-178">ftFloat</span><span class="sxs-lookup"><span data-stu-id="518a7-178">ftFloat</span></span>  <br/> |<span data-ttu-id="518a7-179">0xC</span><span class="sxs-lookup"><span data-stu-id="518a7-179">0xC</span></span>  <br/> |<span data-ttu-id="518a7-180">数值或百分比</span><span class="sxs-lookup"><span data-stu-id="518a7-180">Number or Percent</span></span>  <br/> |
|<span data-ttu-id="518a7-181">ftCurrency</span><span class="sxs-lookup"><span data-stu-id="518a7-181">ftCurrency</span></span>  <br/> |<span data-ttu-id="518a7-182">0xE</span><span class="sxs-lookup"><span data-stu-id="518a7-182">0xE</span></span>  <br/> |<span data-ttu-id="518a7-183">货币</span><span class="sxs-lookup"><span data-stu-id="518a7-183">Currency</span></span>  <br/> |
|<span data-ttu-id="518a7-184">ftCalc</span><span class="sxs-lookup"><span data-stu-id="518a7-184">ftCalc</span></span>  <br/> |<span data-ttu-id="518a7-185">0x12</span><span class="sxs-lookup"><span data-stu-id="518a7-185">0x12</span></span>  <br/> |<span data-ttu-id="518a7-186">公式</span><span class="sxs-lookup"><span data-stu-id="518a7-186">Formula</span></span>  <br/> |
|<span data-ttu-id="518a7-187">ftSwitch</span><span class="sxs-lookup"><span data-stu-id="518a7-187">ftSwitch</span></span>  <br/> |<span data-ttu-id="518a7-188">0x13</span><span class="sxs-lookup"><span data-stu-id="518a7-188">0x13</span></span>  <br/> |<span data-ttu-id="518a7-189">仅显示第一个非空字段-忽略后续字段类型的组合。</span><span class="sxs-lookup"><span data-stu-id="518a7-189">Combination of type showing only the first non-empty field - ignoring subsequent ones.</span></span>  <br/> |
|<span data-ttu-id="518a7-190">ftConcat</span><span class="sxs-lookup"><span data-stu-id="518a7-190">ftConcat</span></span>  <br/> |<span data-ttu-id="518a7-191">0x17</span><span class="sxs-lookup"><span data-stu-id="518a7-191">0x17</span></span>  <br/> |<span data-ttu-id="518a7-192">联接字段及任何文本片断每个其他类型的组合。</span><span class="sxs-lookup"><span data-stu-id="518a7-192">Combination of type joining fields and any text fragments to each other.</span></span>  <br/> |
   
## <a name="folderfielddefinitioncommon-stream-structure"></a><span data-ttu-id="518a7-193">FolderFieldDefinitionCommon 流结构</span><span class="sxs-lookup"><span data-stu-id="518a7-193">FolderFieldDefinitionCommon Stream Structure</span></span>

<span data-ttu-id="518a7-194">FolderFieldDefinitionCommon 流结构包含 FolderFieldDefinitionA 和 FolderFieldDefinitionW 常用的用户定义的字段定义的数据。</span><span class="sxs-lookup"><span data-stu-id="518a7-194">A FolderFieldDefinitionCommon stream structure contains the data of a user-defined field definition that is common to both a FolderFieldDefinitionA and a FolderFieldDefinitionW.</span></span>
  
<span data-ttu-id="518a7-195">此流中的数据元素存储在-little-endian 字节的顺序，紧跟每个其他指定顺序如下：</span><span class="sxs-lookup"><span data-stu-id="518a7-195">Data elements in this stream are stored in little-endian byte order, immediately following each other in the following specified order:</span></span>
  
- <span data-ttu-id="518a7-196">**PropSetGuid**: GUID （16 个字节） 的属性集的文件夹字段对应的 MAPI 属性名的 GUID。</span><span class="sxs-lookup"><span data-stu-id="518a7-196">**PropSetGuid**: GUID (16 bytes), the property set GUID of the folder field's corresponding MAPI property name.</span></span> <span data-ttu-id="518a7-197">此字段的值必须等于 PS_PUBLIC_STRINGS，除非字段类型是**ftNone**在这种情况下，此字段的值必须是等于 GUID_NULL。</span><span class="sxs-lookup"><span data-stu-id="518a7-197">This field's value must be equal to PS_PUBLIC_STRINGS, unless the field type is **ftNone** in which case this field's value must be equal to GUID_NULL.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="518a7-198">出于旧的兼容性，Outlook 可能能够处理不满足此限制某些**PropSetGuid**值，但是这种情况下不包含的此主题。</span><span class="sxs-lookup"><span data-stu-id="518a7-198">For reasons of legacy compatibility, Outlook may be able to handle some **PropSetGuid** values not satisfying this restriction, however such cases are not covered by this topic.</span></span> 
  
- <span data-ttu-id="518a7-199">**fcapm**: DWORD （4 个字节） 下, 表中列出的值以及的含义的零个或多个标志的组合。</span><span class="sxs-lookup"><span data-stu-id="518a7-199">**fcapm**: DWORD (4 bytes), a combination of zero or more flags the values of which and meanings are listed in the following table.</span></span> <span data-ttu-id="518a7-200">具有相同值的标志有取决于该字段的类型，即 FldType 值的含义。</span><span class="sxs-lookup"><span data-stu-id="518a7-200">Flags with the same value have meanings dependent on the field's type, that is, FldType value.</span></span>
    
    |<span data-ttu-id="518a7-201">代表标志名称</span><span class="sxs-lookup"><span data-stu-id="518a7-201">Flag name</span></span>|<span data-ttu-id="518a7-202">值</span><span class="sxs-lookup"><span data-stu-id="518a7-202">Value</span></span>|<span data-ttu-id="518a7-203">含义</span><span class="sxs-lookup"><span data-stu-id="518a7-203">Meaning</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="518a7-204">FCAPM_CAN_EDIT</span><span class="sxs-lookup"><span data-stu-id="518a7-204">FCAPM_CAN_EDIT</span></span>  <br/> |<span data-ttu-id="518a7-205">0x00000001</span><span class="sxs-lookup"><span data-stu-id="518a7-205">0x00000001</span></span>  <br/> |<span data-ttu-id="518a7-206">域是可编辑。</span><span class="sxs-lookup"><span data-stu-id="518a7-206">The field is editable.</span></span>  <br/> |
    |<span data-ttu-id="518a7-207">FCAPM_CAN_SORT</span><span class="sxs-lookup"><span data-stu-id="518a7-207">FCAPM_CAN_SORT</span></span>  <br/> |<span data-ttu-id="518a7-208">0x00000002</span><span class="sxs-lookup"><span data-stu-id="518a7-208">0x00000002</span></span>  <br/> |<span data-ttu-id="518a7-209">字段进行排序。</span><span class="sxs-lookup"><span data-stu-id="518a7-209">The field is sortable.</span></span>  <br/> |
    |<span data-ttu-id="518a7-210">FCAPM_CAN_GROUP</span><span class="sxs-lookup"><span data-stu-id="518a7-210">FCAPM_CAN_GROUP</span></span>  <br/> |<span data-ttu-id="518a7-211">0x00000004</span><span class="sxs-lookup"><span data-stu-id="518a7-211">0x00000004</span></span>  <br/> |<span data-ttu-id="518a7-212">域是树状。</span><span class="sxs-lookup"><span data-stu-id="518a7-212">The field is groupable.</span></span>  <br/> |
    |<span data-ttu-id="518a7-213">FCAPM_MULTILINE_TEXT</span><span class="sxs-lookup"><span data-stu-id="518a7-213">FCAPM_MULTILINE_TEXT</span></span>  <br/> |<span data-ttu-id="518a7-214">0x00000100</span><span class="sxs-lookup"><span data-stu-id="518a7-214">0x00000100</span></span>  <br/> |<span data-ttu-id="518a7-215">字段可以包含多行文本。</span><span class="sxs-lookup"><span data-stu-id="518a7-215">The field can hold multiple lines of text.</span></span>  <br/> |
    |<span data-ttu-id="518a7-216">FCAPM_PERCENT</span><span class="sxs-lookup"><span data-stu-id="518a7-216">FCAPM_PERCENT</span></span>  <br/> |<span data-ttu-id="518a7-217">0x01000000</span><span class="sxs-lookup"><span data-stu-id="518a7-217">0x01000000</span></span>  <br/> |<span data-ttu-id="518a7-218">此字段的类型 ftFloat 是百分比字段。</span><span class="sxs-lookup"><span data-stu-id="518a7-218">This field of the type ftFloat is a percentage field.</span></span>  <br/> |
    |<span data-ttu-id="518a7-219">FCAPM_DATEONLY</span><span class="sxs-lookup"><span data-stu-id="518a7-219">FCAPM_DATEONLY</span></span>  <br/> |<span data-ttu-id="518a7-220">0x01000000</span><span class="sxs-lookup"><span data-stu-id="518a7-220">0x01000000</span></span>  <br/> |<span data-ttu-id="518a7-221">此字段的类型 ftTime 是仅日期时间字段。</span><span class="sxs-lookup"><span data-stu-id="518a7-221">This field of the type ftTime is a date-only time field.</span></span>  <br/> |
    |<span data-ttu-id="518a7-222">FCAPM_UNITLESS</span><span class="sxs-lookup"><span data-stu-id="518a7-222">FCAPM_UNITLESS</span></span>  <br/> |<span data-ttu-id="518a7-223">0x01000000</span><span class="sxs-lookup"><span data-stu-id="518a7-223">0x01000000</span></span>  <br/> |<span data-ttu-id="518a7-224">对于类型 ftInteger 此字段，没有单位允许显示格式;例如此类作为格式"计算机-640 k。..."不允许使用。</span><span class="sxs-lookup"><span data-stu-id="518a7-224">For this field of the type ftInteger, no unit is allowed in display format; for example such formats as "Computer - 640 K…" are not allowed.</span></span>  <br/> |
    |<span data-ttu-id="518a7-225">FCAPM_CAN_EDIT_IN_ITEM</span><span class="sxs-lookup"><span data-stu-id="518a7-225">FCAPM_CAN_EDIT_IN_ITEM</span></span>  <br/> |<span data-ttu-id="518a7-226">0x80000000</span><span class="sxs-lookup"><span data-stu-id="518a7-226">0x80000000</span></span>  <br/> |<span data-ttu-id="518a7-227">字段可编辑项中： 这是专为自定义窗体。</span><span class="sxs-lookup"><span data-stu-id="518a7-227">The field can be edited in the item: This is specifically for custom forms.</span></span>  <br/> |
   
- <span data-ttu-id="518a7-228">**dwString**: DWORD （4 个字节）。</span><span class="sxs-lookup"><span data-stu-id="518a7-228">**dwString**: DWORD (4 bytes).</span></span> <span data-ttu-id="518a7-229">请参阅第一个以下注释。</span><span class="sxs-lookup"><span data-stu-id="518a7-229">See the first following Note.</span></span>
    
- <span data-ttu-id="518a7-230">**dwBitmap**: DWORD （4 个字节）。</span><span class="sxs-lookup"><span data-stu-id="518a7-230">**dwBitmap**: DWORD (4 bytes).</span></span> <span data-ttu-id="518a7-231">请参阅第一个以下注释。</span><span class="sxs-lookup"><span data-stu-id="518a7-231">See the first following Note.</span></span>
    
- <span data-ttu-id="518a7-232">**dwDisplay**: DWORD （4 个字节）。</span><span class="sxs-lookup"><span data-stu-id="518a7-232">**dwDisplay**: DWORD (4 bytes).</span></span> <span data-ttu-id="518a7-233">请参阅第一个以下注释。</span><span class="sxs-lookup"><span data-stu-id="518a7-233">See the first following Note.</span></span>
    
- <span data-ttu-id="518a7-234">**iFmt**: INT （4 个字节）。</span><span class="sxs-lookup"><span data-stu-id="518a7-234">**iFmt**: INT (4 bytes).</span></span> <span data-ttu-id="518a7-235">字段类型具有"格式:"组合框中的"新建域"、"编辑域"和"字段属性"对话框，该组合框中选定的格式的基于 0 的索引。</span><span class="sxs-lookup"><span data-stu-id="518a7-235">For the field types that have the "Format:" combo box in the "New Field", "Edit Field", and "Field Properties" dialogs, the 0-based index of the format selected in that combo box.</span></span> <span data-ttu-id="518a7-236">没有该组合框的字段类型，这必须是 0。</span><span class="sxs-lookup"><span data-stu-id="518a7-236">For the field types without that combo box, this must be 0.</span></span> <span data-ttu-id="518a7-237">该字段的值与字段类型一起唯一确定**dwString**， **dwBitmap**的值并**dwDisplay**字段，，请参阅第一个以下注释。</span><span class="sxs-lookup"><span data-stu-id="518a7-237">The field's value together with the field type uniquely determine the values of the **dwString**, **dwBitmap**, and **dwDisplay** fields, see the first following Note.</span></span>
    
- <span data-ttu-id="518a7-238">**wszFormulaLength**： 单词 （2 个字节）， **wszFormulaLength**数组中的元素的数目。</span><span class="sxs-lookup"><span data-stu-id="518a7-238">**wszFormulaLength**: WORD (2 bytes), the number of elements in the **wszFormulaLength** array.</span></span>
    
- <span data-ttu-id="518a7-239">**wszFormulaLength**: WCHAR 的数组。</span><span class="sxs-lookup"><span data-stu-id="518a7-239">**wszFormulaLength**: An array of WCHAR.</span></span> <span data-ttu-id="518a7-240">这是该字段的公式其标准格式字符串的 Unicode (utf-16) 表示形式。</span><span class="sxs-lookup"><span data-stu-id="518a7-240">This is the Unicode (UTF-16) representation of the field's formula string in its standard format.</span></span> <span data-ttu-id="518a7-241">请参阅标准的说明和 UI 格式的字段的公式的第二个以下注释。</span><span class="sxs-lookup"><span data-stu-id="518a7-241">See the second following Note for the description of the standard and UI formats of a field's formula.</span></span> <span data-ttu-id="518a7-242">此数组的计数等于**wszFormulaLength**。</span><span class="sxs-lookup"><span data-stu-id="518a7-242">The count of this array is equal to **wszFormulaLength**.</span></span> <span data-ttu-id="518a7-243">公式的字符串必须为空字符串，除非字段类型为**ftCalc**、 **ftSwitch**或**ftConcat**。</span><span class="sxs-lookup"><span data-stu-id="518a7-243">The formula string must be an empty string unless the field type is **ftCalc**, **ftSwitch** or **ftConcat**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="518a7-244">尽管**dwString**、 **dwBitmap**和**dwDisplay**的值唯一根据**FldType**值和**iFmt**值，它们是冗余，来确定其正确的值是仍所必需的正确处理 outlook 字段定义。</span><span class="sxs-lookup"><span data-stu-id="518a7-244">Although the values of **dwString**, **dwBitmap**, and **dwDisplay** are uniquely determined based on the **FldType** value and the **iFmt** value, which are redundant, their correct values are still necessary for correct processing of the field definition by Outlook.</span></span> <span data-ttu-id="518a7-245">执行此决定的算法没有简单说明。</span><span class="sxs-lookup"><span data-stu-id="518a7-245">There is no simple description of the algorithm that performs this determination.</span></span> 
> 
> <span data-ttu-id="518a7-246">因此，若要找出哪些**dwString**、 **dwBitmap**和**dwDisplay**值对应于给定的**FldType**值和**iFmt**值，请执行测试通过创建用户定义的字段，该类型，并且所选的格式在**格式**组合框中，假定其适用性，检查为该用户定义的字段创建 Outlook 生成**FolderUserFields**流。</span><span class="sxs-lookup"><span data-stu-id="518a7-246">Therefore, to find out which **dwString**, **dwBitmap**, and **dwDisplay** values correspond to a given **FldType** value and **iFmt** value, perform a test by creating a user-defined field of that type, and with that format selected in the **Format** combo box, assuming its applicability, inspect the resulting **FolderUserFields** stream that Outlook creates for that user-defined field.</span></span> 
  
<span data-ttu-id="518a7-247">在**新域**、**编辑字段**中，和用户定义的字段的**字段属性**对话框的**公式**文本框中编辑其 UI 格式中的字段的公式。</span><span class="sxs-lookup"><span data-stu-id="518a7-247">The field's formula in its UI format is edited in the **Formula** text box of the **New Field**, **Edit Field**, and **Field Properties** dialogs for the user-defined field.</span></span> <span data-ttu-id="518a7-248">要将公式从 UI 格式转换为标准格式的算法取决于该字段类型中以下所述：</span><span class="sxs-lookup"><span data-stu-id="518a7-248">The algorithm to convert a formula from the UI format to the standard format depends on the field type as described in the following:</span></span> 
- <span data-ttu-id="518a7-249">对于类型**ftCalc**和**ftSwitch**的字段，内置域，不是相应的 MAPI 属性的标准格式的命名属性 kind MNID\_字符串，即替换字段名称片段，获得`[<field_name>]`使用片段`[_<field_dispid_decimal>]`。</span><span class="sxs-lookup"><span data-stu-id="518a7-249">For fields of types **ftCalc** and **ftSwitch**, the standard format for built-in fields, which corresponding MAPI properties are not named properties of the kind MNID\_STRING, is obtained by replacing field name fragments, that is `[<field_name>]` with fragments `[_<field_dispid_decimal>]`.</span></span> 

  <span data-ttu-id="518a7-250">例如，如果类型**公式**，即**ftCalc**，与正在美国英语的 Office UI 语言的字段的公式的 UI 格式为`[Business Phone] & [My custom field]`，其中`My custom field`是名称采用的用户定义的字段，此类公式的标准格式`[_14856] & [My custom field]`.</span><span class="sxs-lookup"><span data-stu-id="518a7-250">For example, if the UI format of a formula for a field of the type **Formula**, that is **ftCalc**, with the Office UI language being US English, is `[Business Phone] & [My custom field]`, where `My custom field` is the name of a user-defined field, the standard format of such a formula would be `[_14856] & [My custom field]`.</span></span>

- <span data-ttu-id="518a7-251">对于类型**ftConcat**的字段，可通过执行以下获得标准格式：</span><span class="sxs-lookup"><span data-stu-id="518a7-251">For fields of the type **ftConcat**, the standard format is obtained by performing the following:</span></span>

  1. <span data-ttu-id="518a7-252">截断前导和尾随空白。</span><span class="sxs-lookup"><span data-stu-id="518a7-252">Truncate leading and trailing whitespace.</span></span> 
  2. <span data-ttu-id="518a7-253">分析公式转换为以下两种类型的片段序列：</span><span class="sxs-lookup"><span data-stu-id="518a7-253">Parse the formula into a sequence of fragments of the following two kinds:</span></span> 
     - <span data-ttu-id="518a7-254">用方括号，即，字段名称`[<field_name>]`。</span><span class="sxs-lookup"><span data-stu-id="518a7-254">A field name in square brackets, that is, `[<field_name>]`.</span></span> 
     - <span data-ttu-id="518a7-255">不包含任何方括号子字符串。</span><span class="sxs-lookup"><span data-stu-id="518a7-255">A substring not containing any square brackets.</span></span>   
      <span data-ttu-id="518a7-256">确保没有两个段落的第二类彼此相邻的顺序。</span><span class="sxs-lookup"><span data-stu-id="518a7-256">Assure that no two fragments of the second kind are adjacent in the sequence.</span></span> <span data-ttu-id="518a7-257">如果公式无法分析这种方式，它将被视为无效。</span><span class="sxs-lookup"><span data-stu-id="518a7-257">If the formula cannot be parsed this way, it is considered invalid.</span></span> 
  3. <span data-ttu-id="518a7-258">对于**ftCalc**和**ftSwitch**字段相同的第一类的片段执行替换为相同。</span><span class="sxs-lookup"><span data-stu-id="518a7-258">Perform the same replacement for fragments of the first kind as for the **ftCalc** and **ftSwitch** fields.</span></span> 
  4. <span data-ttu-id="518a7-259">为第二个类型的每个片段，转义所有双引号 (""") 字符，如果有，具有两个连续双引号字符，并将其括在双引号。</span><span class="sxs-lookup"><span data-stu-id="518a7-259">For each fragment of the second kind, escape all double-quote (""") characters, if any, with two consecutive double-quote characters, and enclose it in double quotes.</span></span> 
  5. <span data-ttu-id="518a7-260">插入 & 字符串 (`&`) 相邻片段每对之间。</span><span class="sxs-lookup"><span data-stu-id="518a7-260">Insert an ampersand string (`&`) between each pair of adjacent fragments.</span></span>
 
  <span data-ttu-id="518a7-261">例如，使用美国英语的 Office UI 语言的字段的类型**ftConcat**公式的 UI 格式为时`text1 [Business Phone] "text2" [My custom field]`，其中`My custom field`是用户定义的字段，标准格式的名称，这样的公式很`""text1" & [_14856] & """text2""" & [My custom field]"`。</span><span class="sxs-lookup"><span data-stu-id="518a7-261">For example, using the Office UI language US English, if the UI format of a formula for a field of the type **ftConcat** is `text1 [Business Phone] "text2" [My custom field]`, where `My custom field` is the name of a user-defined field, the standard format for such a formula would be `""text1" & [_14856] & """text2""" & [My custom field]"`.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="518a7-262">另请参阅</span><span class="sxs-lookup"><span data-stu-id="518a7-262">See also</span></span>

- [<span data-ttu-id="518a7-263">FolderUserFields 流示例</span><span class="sxs-lookup"><span data-stu-id="518a7-263">FolderUserFields Stream Sample</span></span>](folderuserfields-stream-sample.md)
- [<span data-ttu-id="518a7-264">为新的用户定义字段添加定义</span><span class="sxs-lookup"><span data-stu-id="518a7-264">Add a Definition for a New User-Defined Field</span></span>](how-to-add-a-definition-for-a-new-user-defined-field.md)
