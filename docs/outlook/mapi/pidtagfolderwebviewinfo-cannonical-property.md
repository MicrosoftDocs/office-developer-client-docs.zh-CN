---
title: PidTagFolderWebViewInfo Cannonical Property
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFolderWebViewInfo
api_type:
- HeaderDef
ms.assetid: 96ea23df-aa4f-4b3e-9663-e7db39f668c1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 70932e703511235e9f5e32efd95b18d1b66494e2
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389958"
---
# <a name="pidtagfolderwebviewinfo-cannonical-property"></a><span data-ttu-id="284c5-103">PidTagFolderWebViewInfo Cannonical Property</span><span class="sxs-lookup"><span data-stu-id="284c5-103">PidTagFolderWebViewInfo Cannonical Property</span></span>

  
  
<span data-ttu-id="284c5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="284c5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="284c5-105">包含在 Microsoft Outlook 中的文件夹主页的 URL。</span><span class="sxs-lookup"><span data-stu-id="284c5-105">Contains the URL for the home page of a folder in Microsoft Outlook.</span></span> <span data-ttu-id="284c5-106">此属性包含调用**WebViewPersistenceObject**二进制流。</span><span class="sxs-lookup"><span data-stu-id="284c5-106">This property contains a binary stream called **WebViewPersistenceObject**.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="284c5-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="284c5-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="284c5-108">PR_FOLDER_WEBVIEWINFO</span><span class="sxs-lookup"><span data-stu-id="284c5-108">PR_FOLDER_WEBVIEWINFO</span></span>  <br/> |
|<span data-ttu-id="284c5-109">标识符：</span><span class="sxs-lookup"><span data-stu-id="284c5-109">Identifier:</span></span>  <br/> |<span data-ttu-id="284c5-110">0x36DF</span><span class="sxs-lookup"><span data-stu-id="284c5-110">0x36DF</span></span>  <br/> |
|<span data-ttu-id="284c5-111">数据类型：</span><span class="sxs-lookup"><span data-stu-id="284c5-111">Data type:</span></span>  <br/> |<span data-ttu-id="284c5-112">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="284c5-112">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="284c5-113">区域：</span><span class="sxs-lookup"><span data-stu-id="284c5-113">Area:</span></span>  <br/> |<span data-ttu-id="284c5-114">MAPI 文件夹</span><span class="sxs-lookup"><span data-stu-id="284c5-114">MAPI folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="284c5-115">说明</span><span class="sxs-lookup"><span data-stu-id="284c5-115">Remarks</span></span>

<span data-ttu-id="284c5-116">可为指定的任何 Outlook 文件夹主页 URL。</span><span class="sxs-lookup"><span data-stu-id="284c5-116">A home page URL can be specified for any Outlook folder.</span></span> <span data-ttu-id="284c5-117">从属性对话框的文件夹的**主页**选项卡，可以在 Outlook 中访问此信息。</span><span class="sxs-lookup"><span data-stu-id="284c5-117">This information can be accessed in Outlook from the **Home Page** tab of the Properties dialog box for a folder.</span></span> 
  
<span data-ttu-id="284c5-118">根据特定的策略设置，主页可能被忽略 outlook 的 MAPI 存储区包含此文件夹不在其[IMSCapabilities::GetCapabilities](pidtagfolderwebviewinfo-cannonical-property.md)实现报告 MSCAP_SECURE_FOLDER_HOMEPAGES。</span><span class="sxs-lookup"><span data-stu-id="284c5-118">Depending on certain policy settings, the home page might be ignored by Outlook if the MAPI store that contains this folder does not report MSCAP_SECURE_FOLDER_HOMEPAGES in its [IMSCapabilities::GetCapabilities](pidtagfolderwebviewinfo-cannonical-property.md) implementation.</span></span> 
  
<span data-ttu-id="284c5-119">**Outlook 今日**文件夹和公用文件夹可以具有主页的 Url。</span><span class="sxs-lookup"><span data-stu-id="284c5-119">Both the **Outlook Today** folder and a public folder can have home page URLs.</span></span> <span data-ttu-id="284c5-120">**Outlook 今日**文件夹但是使用另一种机制来管理其主页 URL;本主题中未涵盖的机制。</span><span class="sxs-lookup"><span data-stu-id="284c5-120">However the **Outlook Today** folder uses a different mechanism to manage its home page URL; that mechanism is not covered in this topic.</span></span> <span data-ttu-id="284c5-121">公用文件夹可能还需要在其中定义特定于用户的主页 URL。</span><span class="sxs-lookup"><span data-stu-id="284c5-121">A public folder might also have a home page URL defined in it that is specific to a user.</span></span> <span data-ttu-id="284c5-122">但是，该功能不在本主题中所述。</span><span class="sxs-lookup"><span data-stu-id="284c5-122">However, that capability is not described in this topic.</span></span> 
  
<span data-ttu-id="284c5-123">此属性的值是调用**WebViewPersistenceObject**二进制流。</span><span class="sxs-lookup"><span data-stu-id="284c5-123">The value of this property is a binary stream called **WebViewPersistenceObject**.</span></span>
  
### <a name="webviewpersistenceobject-stream-structure"></a><span data-ttu-id="284c5-124">WebViewPersistenceObject 流结构</span><span class="sxs-lookup"><span data-stu-id="284c5-124">WebViewPersistenceObject Stream Structure</span></span>

<span data-ttu-id="284c5-125">**WebViewPersistenceObject**流结构包含有关某个文件夹主页 URL 的信息。</span><span class="sxs-lookup"><span data-stu-id="284c5-125">The **WebViewPersistenceObject** stream structure contains information about a home page URL for a folder.</span></span> 
  
<span data-ttu-id="284c5-126">此结构中的数据元素存储在-little-endian 字节的顺序，紧跟相互按照下面指定的顺序。</span><span class="sxs-lookup"><span data-stu-id="284c5-126">Data elements in this structure are stored in little-endian byte order, immediately following one another in the following specified order.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="284c5-127">以下说明可能不会列出所有 Outlook; 支持的字段值因此，当您的代码读取现有流时，可能还发现此处未列出一些标志。</span><span class="sxs-lookup"><span data-stu-id="284c5-127">The following description may not list all of the field values supported by Outlook; therefore, when your code reads an existing stream, some flags that are not listed here might also be found.</span></span> <span data-ttu-id="284c5-128">但是，该说明可用于以编程方式创建 Outlook 将了解**PidTagFolderWebViewInfo**属性的值。</span><span class="sxs-lookup"><span data-stu-id="284c5-128">However, you can use this description to programmatically create values for the **PidTagFolderWebViewInfo** property that Outlook will understand.</span></span> 
  
 <span data-ttu-id="284c5-129">_dwVersion_</span><span class="sxs-lookup"><span data-stu-id="284c5-129">_dwVersion_</span></span>
  
> <span data-ttu-id="284c5-130">DWORD （4 个字节）。</span><span class="sxs-lookup"><span data-stu-id="284c5-130">DWORD (4 bytes).</span></span> <span data-ttu-id="284c5-131">结构的格式的版本。</span><span class="sxs-lookup"><span data-stu-id="284c5-131">The version of the structure's format.</span></span> <span data-ttu-id="284c5-132">从 Microsoft Office Outlook 2007 中，该字段仅受支持的值如下所示。</span><span class="sxs-lookup"><span data-stu-id="284c5-132">As of Microsoft Office Outlook 2007, the only supported value for this field is as follows.</span></span>
    
|<span data-ttu-id="284c5-133">**值名称**</span><span class="sxs-lookup"><span data-stu-id="284c5-133">**Value name**</span></span>|<span data-ttu-id="284c5-134">**值**</span><span class="sxs-lookup"><span data-stu-id="284c5-134">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="284c5-135">WEBVIEW_PERSISTENCE_VERSION</span><span class="sxs-lookup"><span data-stu-id="284c5-135">WEBVIEW_PERSISTENCE_VERSION</span></span>  <br/> |<span data-ttu-id="284c5-136">0x00000002</span><span class="sxs-lookup"><span data-stu-id="284c5-136">0x00000002</span></span>  <br/> |
   
 <span data-ttu-id="284c5-137">_dwType_</span><span class="sxs-lookup"><span data-stu-id="284c5-137">_dwType_</span></span>
  
> <span data-ttu-id="284c5-138">DWORD （4 个字节）。</span><span class="sxs-lookup"><span data-stu-id="284c5-138">DWORD (4 bytes).</span></span> <span data-ttu-id="284c5-139">主页信息的类型。</span><span class="sxs-lookup"><span data-stu-id="284c5-139">The type of the home page information.</span></span> <span data-ttu-id="284c5-140">从 Microsoft Office Outlook 2007 中，该字段仅受支持的值如下所示。</span><span class="sxs-lookup"><span data-stu-id="284c5-140">As of Microsoft Office Outlook 2007, the only supported value for this field is as follows.</span></span>
    
|<span data-ttu-id="284c5-141">**值名称**</span><span class="sxs-lookup"><span data-stu-id="284c5-141">**Value name**</span></span>|<span data-ttu-id="284c5-142">**值**</span><span class="sxs-lookup"><span data-stu-id="284c5-142">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="284c5-143">WEBVIEWURL</span><span class="sxs-lookup"><span data-stu-id="284c5-143">WEBVIEWURL</span></span>  <br/> |<span data-ttu-id="284c5-144">0x00000001</span><span class="sxs-lookup"><span data-stu-id="284c5-144">0x00000001</span></span>  <br/> |
   
 <span data-ttu-id="284c5-145">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="284c5-145">_dwFlags_</span></span>
  
> <span data-ttu-id="284c5-146">DWORD （4 个字节）。</span><span class="sxs-lookup"><span data-stu-id="284c5-146">DWORD (4 bytes).</span></span> <span data-ttu-id="284c5-147">零个或更多的组合标记其值并在下表中列出的含义。</span><span class="sxs-lookup"><span data-stu-id="284c5-147">A combination of zero or more flags whose values and meanings are listed in the following table.</span></span>
    
|<span data-ttu-id="284c5-148">标志名称 \*\*\*</span><span class="sxs-lookup"><span data-stu-id="284c5-148">\*\*\*\*Flag name\*\*\*\*</span></span>|<span data-ttu-id="284c5-149">\*\*\*\*值\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="284c5-149">\*\*\*\*Value\*\*\*\*</span></span>|<span data-ttu-id="284c5-150">\*\*\*\*说明\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="284c5-150">\*\*\*\*Description\*\*\*\*</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="284c5-151">WEBVIEW_FLAGS_SHOWBYDEFAULT</span><span class="sxs-lookup"><span data-stu-id="284c5-151">WEBVIEW_FLAGS_SHOWBYDEFAULT</span></span>  <br/> |<span data-ttu-id="284c5-152">0x00000001</span><span class="sxs-lookup"><span data-stu-id="284c5-152">0x00000001</span></span>  <br/> |<span data-ttu-id="284c5-153">**显示默认情况下，此文件夹主页**复选框已签入的文件夹的属性对话框的**主页**选项卡。</span><span class="sxs-lookup"><span data-stu-id="284c5-153">The **Show home page by default for this folder** check box was checked in the **Home Page** tab of the Properties dialog box for a folder.</span></span>  <br/> |
   
 <span data-ttu-id="284c5-154">_dwUnused [7]_</span><span class="sxs-lookup"><span data-stu-id="284c5-154">_dwUnused[7]_</span></span>
  
> <span data-ttu-id="284c5-155">7 DWORD 元素 （28 字节） 的数组。</span><span class="sxs-lookup"><span data-stu-id="284c5-155">An array of 7 DWORD elements (28 bytes total).</span></span> <span data-ttu-id="284c5-156">未使用。</span><span class="sxs-lookup"><span data-stu-id="284c5-156">Unused.</span></span>
    
<span data-ttu-id="284c5-157">cbData</span><span class="sxs-lookup"><span data-stu-id="284c5-157">cbData</span></span>
  
> <span data-ttu-id="284c5-158">ULONG （4 个字节）。</span><span class="sxs-lookup"><span data-stu-id="284c5-158">A ULONG (4 bytes).</span></span> <span data-ttu-id="284c5-159">以字节为单位的_wzURL_数据元素的大小。</span><span class="sxs-lookup"><span data-stu-id="284c5-159">The size, in bytes, of the  _wzURL_ data element.</span></span> 
    
 <span data-ttu-id="284c5-160">_wzURL_</span><span class="sxs-lookup"><span data-stu-id="284c5-160">_wzURL_</span></span>
  
> <span data-ttu-id="284c5-161">WCHAR 元素的数组。</span><span class="sxs-lookup"><span data-stu-id="284c5-161">An array of WCHAR elements.</span></span> <span data-ttu-id="284c5-162">Utf-16 字符串表示形式零结尾主页的 URL。</span><span class="sxs-lookup"><span data-stu-id="284c5-162">The UTF-16 representation of the zero-terminated home page URL string.</span></span>
    
### <a name="webviewpersistenceobject-stream-sample"></a><span data-ttu-id="284c5-163">WebViewPersistenceObject 流示例</span><span class="sxs-lookup"><span data-stu-id="284c5-163">WebViewPersistenceObject Stream Sample</span></span>

<span data-ttu-id="284c5-164">本节介绍**WebViewPersistenceObject**流的示例。</span><span class="sxs-lookup"><span data-stu-id="284c5-164">This section describes an example of a **WebViewPersistenceObject** stream.</span></span> <span data-ttu-id="284c5-165">Stream 指定的主页上 URL"https://www.microsoft.com"。</span><span class="sxs-lookup"><span data-stu-id="284c5-165">The stream specifies the home page URL "https://www.microsoft.com".</span></span> 
  
 <span data-ttu-id="284c5-166">**数据转储**</span><span class="sxs-lookup"><span data-stu-id="284c5-166">**Data dump**</span></span>
  
<span data-ttu-id="284c5-167">下面是流的它将二进制编辑器中显示数据转储。</span><span class="sxs-lookup"><span data-stu-id="284c5-167">The following is a data dump of the stream as it would be displayed in a binary editor.</span></span>
  
|<span data-ttu-id="284c5-168">**流偏移**</span><span class="sxs-lookup"><span data-stu-id="284c5-168">**Stream offset**</span></span>|<span data-ttu-id="284c5-169">**数据字节**</span><span class="sxs-lookup"><span data-stu-id="284c5-169">**Data bytes**</span></span>|<span data-ttu-id="284c5-170">**ASCII 数据**</span><span class="sxs-lookup"><span data-stu-id="284c5-170">**ASCII data**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="284c5-171">0000000000</span><span class="sxs-lookup"><span data-stu-id="284c5-171">0000000000</span></span>  <br/> | `02 00 00 00 01 00 00 00 01 00 00 00 00 00 00 00` <br/> | `?...?...?.......` <br/> |
|<span data-ttu-id="284c5-172">0000000010</span><span class="sxs-lookup"><span data-stu-id="284c5-172">0000000010</span></span>  <br/> | `00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00` <br/> | `................` <br/> |
|<span data-ttu-id="284c5-173">0000000020</span><span class="sxs-lookup"><span data-stu-id="284c5-173">0000000020</span></span>  <br/> | `00 00 00 00 00 00 00 00 32 00 00 00 68 00 74 00` <br/> | `........2...h.t.` <br/> |
|<span data-ttu-id="284c5-174">0000000030</span><span class="sxs-lookup"><span data-stu-id="284c5-174">0000000030</span></span>  <br/> | `74 00 70 00 3A 00 2F 00 2F 00 77 00 77 00 77 00` <br/> | `t.p.:././.w.w.w.` <br/> |
|<span data-ttu-id="284c5-175">0000000040</span><span class="sxs-lookup"><span data-stu-id="284c5-175">0000000040</span></span>  <br/> | `2E 00 6D 00 69 00 63 00 72 00 6F 00 73 00 6F 00` <br/> | `..m.i.c.r.o.s.o.` <br/> |
|<span data-ttu-id="284c5-176">0000000050</span><span class="sxs-lookup"><span data-stu-id="284c5-176">0000000050</span></span>  <br/> | `66 00 74 00 2E 00 63 00 6F 00 6D 00 00 00` <br/> | `f.t...c.o.m...` <br/> |
   
<span data-ttu-id="284c5-177">下面是**WebViewPersistenceObject**流的示例数据的分析。</span><span class="sxs-lookup"><span data-stu-id="284c5-177">The following is a parse of the sample data for the **WebViewPersistenceObject** stream.</span></span> 
  
 <span data-ttu-id="284c5-178">_dwVersion_</span><span class="sxs-lookup"><span data-stu-id="284c5-178">_dwVersion_</span></span>
  
> <span data-ttu-id="284c5-179">偏移 0x0，4 个字节： 0x00000002:uc (WEBVIEW_PERSISTENCE_VERSION)。</span><span class="sxs-lookup"><span data-stu-id="284c5-179">Offset 0x0, 4 bytes: 0x00000002 (WEBVIEW_PERSISTENCE_VERSION).</span></span>
    
 <span data-ttu-id="284c5-180">_dwType_</span><span class="sxs-lookup"><span data-stu-id="284c5-180">_dwType_</span></span>
  
> <span data-ttu-id="284c5-181">偏移 0x4，4 个字节： 0x00000001 (WEBVIEWURL)。</span><span class="sxs-lookup"><span data-stu-id="284c5-181">Offset 0x4, 4 bytes: 0x00000001 (WEBVIEWURL).</span></span>
    
 <span data-ttu-id="284c5-182">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="284c5-182">_dwFlags_</span></span>
  
> <span data-ttu-id="284c5-183">偏移 0x8，4 个字节： 0x00000001 (WEBVIEW_FLAGS_SHOWBYDEFAULT)。</span><span class="sxs-lookup"><span data-stu-id="284c5-183">Offset 0x8, 4 bytes: 0x00000001 (WEBVIEW_FLAGS_SHOWBYDEFAULT).</span></span>
    
 <span data-ttu-id="284c5-184">_dwUnused [7]_</span><span class="sxs-lookup"><span data-stu-id="284c5-184">_dwUnused[7]_</span></span>
  
> <span data-ttu-id="284c5-185">偏移 0xC，28 字节： 所有零。</span><span class="sxs-lookup"><span data-stu-id="284c5-185">Offset 0xC, 28 bytes: all zeros.</span></span>
    
 <span data-ttu-id="284c5-186">_cbData_</span><span class="sxs-lookup"><span data-stu-id="284c5-186">_cbData_</span></span>
  
> <span data-ttu-id="284c5-187">偏移 0x28，4 个字节： 0x00000032。</span><span class="sxs-lookup"><span data-stu-id="284c5-187">Offset 0x28, 4 bytes: 0x00000032.</span></span>
    
 <span data-ttu-id="284c5-188">_wzURL_</span><span class="sxs-lookup"><span data-stu-id="284c5-188">_wzURL_</span></span>
  
> <span data-ttu-id="284c5-189">偏移量 0x2C，0x32 字节： 25 WCHARs 的数组。</span><span class="sxs-lookup"><span data-stu-id="284c5-189">Offset 0x2C, 0x32 bytes: array of 25 WCHARs.</span></span> <span data-ttu-id="284c5-190">一个 Unicode 零结尾字符串值:"https://www.microsoft.com"。</span><span class="sxs-lookup"><span data-stu-id="284c5-190">A Unicode zero-terminated string value: "https://www.microsoft.com".</span></span>
    

