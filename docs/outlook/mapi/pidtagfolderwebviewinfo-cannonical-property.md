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
ms.openlocfilehash: eec8ea4b4ddee8b6c399bbb4871c286fea4fae3d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588403"
---
# <a name="pidtagfolderwebviewinfo-cannonical-property"></a><span data-ttu-id="25379-103">PidTagFolderWebViewInfo Cannonical Property</span><span class="sxs-lookup"><span data-stu-id="25379-103">PidTagFolderWebViewInfo Cannonical Property</span></span>

  
  
<span data-ttu-id="25379-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="25379-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="25379-105">包含在 Microsoft Outlook 中的文件夹主页的 URL。</span><span class="sxs-lookup"><span data-stu-id="25379-105">Contains the URL for the home page of a folder in Microsoft Outlook.</span></span> <span data-ttu-id="25379-106">此属性包含调用**WebViewPersistenceObject**二进制流。</span><span class="sxs-lookup"><span data-stu-id="25379-106">This property contains a binary stream called **WebViewPersistenceObject**.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="25379-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="25379-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="25379-108">PR_FOLDER_WEBVIEWINFO</span><span class="sxs-lookup"><span data-stu-id="25379-108">PR_FOLDER_WEBVIEWINFO</span></span>  <br/> |
|<span data-ttu-id="25379-109">标识符：</span><span class="sxs-lookup"><span data-stu-id="25379-109">Identifier:</span></span>  <br/> |<span data-ttu-id="25379-110">0x36DF</span><span class="sxs-lookup"><span data-stu-id="25379-110">0x36DF</span></span>  <br/> |
|<span data-ttu-id="25379-111">数据类型：</span><span class="sxs-lookup"><span data-stu-id="25379-111">Data type:</span></span>  <br/> |<span data-ttu-id="25379-112">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="25379-112">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="25379-113">区域：</span><span class="sxs-lookup"><span data-stu-id="25379-113">Area:</span></span>  <br/> |<span data-ttu-id="25379-114">MAPI 文件夹</span><span class="sxs-lookup"><span data-stu-id="25379-114">MAPI folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="25379-115">注解</span><span class="sxs-lookup"><span data-stu-id="25379-115">Remarks</span></span>

<span data-ttu-id="25379-116">可为指定的任何 Outlook 文件夹主页 URL。</span><span class="sxs-lookup"><span data-stu-id="25379-116">A home page URL can be specified for any Outlook folder.</span></span> <span data-ttu-id="25379-117">从属性对话框的文件夹的**主页**选项卡，可以在 Outlook 中访问此信息。</span><span class="sxs-lookup"><span data-stu-id="25379-117">This information can be accessed in Outlook from the **Home Page** tab of the Properties dialog box for a folder.</span></span> 
  
<span data-ttu-id="25379-118">根据特定的策略设置，主页可能被忽略 outlook 的 MAPI 存储区包含此文件夹不在其[IMSCapabilities::GetCapabilities](pidtagfolderwebviewinfo-cannonical-property.md)实现报告 MSCAP_SECURE_FOLDER_HOMEPAGES。</span><span class="sxs-lookup"><span data-stu-id="25379-118">Depending on certain policy settings, the home page might be ignored by Outlook if the MAPI store that contains this folder does not report MSCAP_SECURE_FOLDER_HOMEPAGES in its [IMSCapabilities::GetCapabilities](pidtagfolderwebviewinfo-cannonical-property.md) implementation.</span></span> 
  
<span data-ttu-id="25379-119">**Outlook 今日**文件夹和公用文件夹可以具有主页的 Url。</span><span class="sxs-lookup"><span data-stu-id="25379-119">Both the **Outlook Today** folder and a public folder can have home page URLs.</span></span> <span data-ttu-id="25379-120">**Outlook 今日**文件夹但是使用另一种机制来管理其主页 URL;本主题中未涵盖的机制。</span><span class="sxs-lookup"><span data-stu-id="25379-120">However the **Outlook Today** folder uses a different mechanism to manage its home page URL; that mechanism is not covered in this topic.</span></span> <span data-ttu-id="25379-121">公用文件夹可能还需要在其中定义特定于用户的主页 URL。</span><span class="sxs-lookup"><span data-stu-id="25379-121">A public folder might also have a home page URL defined in it that is specific to a user.</span></span> <span data-ttu-id="25379-122">但是，该功能不在本主题中所述。</span><span class="sxs-lookup"><span data-stu-id="25379-122">However, that capability is not described in this topic.</span></span> 
  
<span data-ttu-id="25379-123">此属性的值是调用**WebViewPersistenceObject**二进制流。</span><span class="sxs-lookup"><span data-stu-id="25379-123">The value of this property is a binary stream called **WebViewPersistenceObject**.</span></span>
  
### <a name="webviewpersistenceobject-stream-structure"></a><span data-ttu-id="25379-124">WebViewPersistenceObject 流结构</span><span class="sxs-lookup"><span data-stu-id="25379-124">WebViewPersistenceObject Stream Structure</span></span>

<span data-ttu-id="25379-125">**WebViewPersistenceObject**流结构包含有关某个文件夹主页 URL 的信息。</span><span class="sxs-lookup"><span data-stu-id="25379-125">The **WebViewPersistenceObject** stream structure contains information about a home page URL for a folder.</span></span> 
  
<span data-ttu-id="25379-126">此结构中的数据元素存储在-little-endian 字节的顺序，紧跟相互按照下面指定的顺序。</span><span class="sxs-lookup"><span data-stu-id="25379-126">Data elements in this structure are stored in little-endian byte order, immediately following one another in the following specified order.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="25379-127">以下说明可能不会列出所有 Outlook; 支持的字段值因此，当您的代码读取现有流时，可能还发现此处未列出一些标志。</span><span class="sxs-lookup"><span data-stu-id="25379-127">The following description may not list all of the field values supported by Outlook; therefore, when your code reads an existing stream, some flags that are not listed here might also be found.</span></span> <span data-ttu-id="25379-128">但是，该说明可用于以编程方式创建 Outlook 将了解**PidTagFolderWebViewInfo**属性的值。</span><span class="sxs-lookup"><span data-stu-id="25379-128">However, you can use this description to programmatically create values for the **PidTagFolderWebViewInfo** property that Outlook will understand.</span></span> 
  
 <span data-ttu-id="25379-129">_dwVersion_</span><span class="sxs-lookup"><span data-stu-id="25379-129">_dwVersion_</span></span>
  
> <span data-ttu-id="25379-130">DWORD （4 个字节）。</span><span class="sxs-lookup"><span data-stu-id="25379-130">DWORD (4 bytes).</span></span> <span data-ttu-id="25379-131">结构的格式的版本。</span><span class="sxs-lookup"><span data-stu-id="25379-131">The version of the structure's format.</span></span> <span data-ttu-id="25379-132">从 Microsoft Office Outlook 2007 中，该字段仅受支持的值如下所示。</span><span class="sxs-lookup"><span data-stu-id="25379-132">As of Microsoft Office Outlook 2007, the only supported value for this field is as follows.</span></span>
    
|<span data-ttu-id="25379-133">**值名称**</span><span class="sxs-lookup"><span data-stu-id="25379-133">**Value name**</span></span>|<span data-ttu-id="25379-134">**值**</span><span class="sxs-lookup"><span data-stu-id="25379-134">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="25379-135">WEBVIEW_PERSISTENCE_VERSION</span><span class="sxs-lookup"><span data-stu-id="25379-135">WEBVIEW_PERSISTENCE_VERSION</span></span>  <br/> |<span data-ttu-id="25379-136">0x00000002</span><span class="sxs-lookup"><span data-stu-id="25379-136">0x00000002</span></span>  <br/> |
   
 <span data-ttu-id="25379-137">_dwType_</span><span class="sxs-lookup"><span data-stu-id="25379-137">_dwType_</span></span>
  
> <span data-ttu-id="25379-138">DWORD （4 个字节）。</span><span class="sxs-lookup"><span data-stu-id="25379-138">DWORD (4 bytes).</span></span> <span data-ttu-id="25379-139">主页信息的类型。</span><span class="sxs-lookup"><span data-stu-id="25379-139">The type of the home page information.</span></span> <span data-ttu-id="25379-140">从 Microsoft Office Outlook 2007 中，该字段仅受支持的值如下所示。</span><span class="sxs-lookup"><span data-stu-id="25379-140">As of Microsoft Office Outlook 2007, the only supported value for this field is as follows.</span></span>
    
|<span data-ttu-id="25379-141">**值名称**</span><span class="sxs-lookup"><span data-stu-id="25379-141">**Value name**</span></span>|<span data-ttu-id="25379-142">**值**</span><span class="sxs-lookup"><span data-stu-id="25379-142">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="25379-143">WEBVIEWURL</span><span class="sxs-lookup"><span data-stu-id="25379-143">WEBVIEWURL</span></span>  <br/> |<span data-ttu-id="25379-144">0x00000001</span><span class="sxs-lookup"><span data-stu-id="25379-144">0x00000001</span></span>  <br/> |
   
 <span data-ttu-id="25379-145">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="25379-145">_dwFlags_</span></span>
  
> <span data-ttu-id="25379-146">DWORD （4 个字节）。</span><span class="sxs-lookup"><span data-stu-id="25379-146">DWORD (4 bytes).</span></span> <span data-ttu-id="25379-147">零个或更多的组合标记其值并在下表中列出的含义。</span><span class="sxs-lookup"><span data-stu-id="25379-147">A combination of zero or more flags whose values and meanings are listed in the following table.</span></span>
    
|<span data-ttu-id="25379-148">标志名称 \*\*\*</span><span class="sxs-lookup"><span data-stu-id="25379-148">****Flag name****</span></span>|<span data-ttu-id="25379-149">****值****</span><span class="sxs-lookup"><span data-stu-id="25379-149">****Value****</span></span>|<span data-ttu-id="25379-150">****说明****</span><span class="sxs-lookup"><span data-stu-id="25379-150">****Description****</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="25379-151">WEBVIEW_FLAGS_SHOWBYDEFAULT</span><span class="sxs-lookup"><span data-stu-id="25379-151">WEBVIEW_FLAGS_SHOWBYDEFAULT</span></span>  <br/> |<span data-ttu-id="25379-152">0x00000001</span><span class="sxs-lookup"><span data-stu-id="25379-152">0x00000001</span></span>  <br/> |<span data-ttu-id="25379-153">**显示默认情况下，此文件夹主页**复选框已签入的文件夹的属性对话框的**主页**选项卡。</span><span class="sxs-lookup"><span data-stu-id="25379-153">The **Show home page by default for this folder** check box was checked in the **Home Page** tab of the Properties dialog box for a folder.</span></span>  <br/> |
   
 <span data-ttu-id="25379-154">_dwUnused [7]_</span><span class="sxs-lookup"><span data-stu-id="25379-154">_dwUnused[7]_</span></span>
  
> <span data-ttu-id="25379-155">7 DWORD 元素 （28 字节） 的数组。</span><span class="sxs-lookup"><span data-stu-id="25379-155">An array of 7 DWORD elements (28 bytes total).</span></span> <span data-ttu-id="25379-156">未使用。</span><span class="sxs-lookup"><span data-stu-id="25379-156">Unused.</span></span>
    
<span data-ttu-id="25379-157">cbData</span><span class="sxs-lookup"><span data-stu-id="25379-157">cbData</span></span>
  
> <span data-ttu-id="25379-158">ULONG （4 个字节）。</span><span class="sxs-lookup"><span data-stu-id="25379-158">A ULONG (4 bytes).</span></span> <span data-ttu-id="25379-159">以字节为单位的_wzURL_数据元素的大小。</span><span class="sxs-lookup"><span data-stu-id="25379-159">The size, in bytes, of the  _wzURL_ data element.</span></span> 
    
 <span data-ttu-id="25379-160">_wzURL_</span><span class="sxs-lookup"><span data-stu-id="25379-160">_wzURL_</span></span>
  
> <span data-ttu-id="25379-161">WCHAR 元素的数组。</span><span class="sxs-lookup"><span data-stu-id="25379-161">An array of WCHAR elements.</span></span> <span data-ttu-id="25379-162">Utf-16 字符串表示形式零结尾主页的 URL。</span><span class="sxs-lookup"><span data-stu-id="25379-162">The UTF-16 representation of the zero-terminated home page URL string.</span></span>
    
### <a name="webviewpersistenceobject-stream-sample"></a><span data-ttu-id="25379-163">WebViewPersistenceObject 流示例</span><span class="sxs-lookup"><span data-stu-id="25379-163">WebViewPersistenceObject Stream Sample</span></span>

<span data-ttu-id="25379-164">本节介绍**WebViewPersistenceObject**流的示例。</span><span class="sxs-lookup"><span data-stu-id="25379-164">This section describes an example of a **WebViewPersistenceObject** stream.</span></span> <span data-ttu-id="25379-165">Stream 指定的主页上 URL"http://www.microsoft.com"。</span><span class="sxs-lookup"><span data-stu-id="25379-165">The stream specifies the home page URL "http://www.microsoft.com".</span></span> 
  
 <span data-ttu-id="25379-166">**数据转储**</span><span class="sxs-lookup"><span data-stu-id="25379-166">**Data dump**</span></span>
  
<span data-ttu-id="25379-167">下面是流的它将二进制编辑器中显示数据转储。</span><span class="sxs-lookup"><span data-stu-id="25379-167">The following is a data dump of the stream as it would be displayed in a binary editor.</span></span>
  
|<span data-ttu-id="25379-168">**流偏移**</span><span class="sxs-lookup"><span data-stu-id="25379-168">**Stream offset**</span></span>|<span data-ttu-id="25379-169">**数据字节**</span><span class="sxs-lookup"><span data-stu-id="25379-169">**Data bytes**</span></span>|<span data-ttu-id="25379-170">**ASCII 数据**</span><span class="sxs-lookup"><span data-stu-id="25379-170">**ASCII data**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="25379-171">0000000000</span><span class="sxs-lookup"><span data-stu-id="25379-171">0000000000</span></span>  <br/> | `02 00 00 00 01 00 00 00 01 00 00 00 00 00 00 00` <br/> | `?...?...?.......` <br/> |
|<span data-ttu-id="25379-172">0000000010</span><span class="sxs-lookup"><span data-stu-id="25379-172">0000000010</span></span>  <br/> | `00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00` <br/> | `................` <br/> |
|<span data-ttu-id="25379-173">0000000020</span><span class="sxs-lookup"><span data-stu-id="25379-173">0000000020</span></span>  <br/> | `00 00 00 00 00 00 00 00 32 00 00 00 68 00 74 00` <br/> | `........2...h.t.` <br/> |
|<span data-ttu-id="25379-174">0000000030</span><span class="sxs-lookup"><span data-stu-id="25379-174">0000000030</span></span>  <br/> | `74 00 70 00 3A 00 2F 00 2F 00 77 00 77 00 77 00` <br/> | `t.p.:././.w.w.w.` <br/> |
|<span data-ttu-id="25379-175">0000000040</span><span class="sxs-lookup"><span data-stu-id="25379-175">0000000040</span></span>  <br/> | `2E 00 6D 00 69 00 63 00 72 00 6F 00 73 00 6F 00` <br/> | `..m.i.c.r.o.s.o.` <br/> |
|<span data-ttu-id="25379-176">0000000050</span><span class="sxs-lookup"><span data-stu-id="25379-176">0000000050</span></span>  <br/> | `66 00 74 00 2E 00 63 00 6F 00 6D 00 00 00` <br/> | `f.t...c.o.m...` <br/> |
   
<span data-ttu-id="25379-177">下面是**WebViewPersistenceObject**流的示例数据的分析。</span><span class="sxs-lookup"><span data-stu-id="25379-177">The following is a parse of the sample data for the **WebViewPersistenceObject** stream.</span></span> 
  
 <span data-ttu-id="25379-178">_dwVersion_</span><span class="sxs-lookup"><span data-stu-id="25379-178">_dwVersion_</span></span>
  
> <span data-ttu-id="25379-179">偏移 0x0，4 个字节： 0x00000002:uc (WEBVIEW_PERSISTENCE_VERSION)。</span><span class="sxs-lookup"><span data-stu-id="25379-179">Offset 0x0, 4 bytes: 0x00000002 (WEBVIEW_PERSISTENCE_VERSION).</span></span>
    
 <span data-ttu-id="25379-180">_dwType_</span><span class="sxs-lookup"><span data-stu-id="25379-180">_dwType_</span></span>
  
> <span data-ttu-id="25379-181">偏移 0x4，4 个字节： 0x00000001 (WEBVIEWURL)。</span><span class="sxs-lookup"><span data-stu-id="25379-181">Offset 0x4, 4 bytes: 0x00000001 (WEBVIEWURL).</span></span>
    
 <span data-ttu-id="25379-182">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="25379-182">_dwFlags_</span></span>
  
> <span data-ttu-id="25379-183">偏移 0x8，4 个字节： 0x00000001 (WEBVIEW_FLAGS_SHOWBYDEFAULT)。</span><span class="sxs-lookup"><span data-stu-id="25379-183">Offset 0x8, 4 bytes: 0x00000001 (WEBVIEW_FLAGS_SHOWBYDEFAULT).</span></span>
    
 <span data-ttu-id="25379-184">_dwUnused [7]_</span><span class="sxs-lookup"><span data-stu-id="25379-184">_dwUnused[7]_</span></span>
  
> <span data-ttu-id="25379-185">偏移 0xC，28 字节： 所有零。</span><span class="sxs-lookup"><span data-stu-id="25379-185">Offset 0xC, 28 bytes: all zeros.</span></span>
    
 <span data-ttu-id="25379-186">_cbData_</span><span class="sxs-lookup"><span data-stu-id="25379-186">_cbData_</span></span>
  
> <span data-ttu-id="25379-187">偏移 0x28，4 个字节： 0x00000032。</span><span class="sxs-lookup"><span data-stu-id="25379-187">Offset 0x28, 4 bytes: 0x00000032.</span></span>
    
 <span data-ttu-id="25379-188">_wzURL_</span><span class="sxs-lookup"><span data-stu-id="25379-188">_wzURL_</span></span>
  
> <span data-ttu-id="25379-189">偏移量 0x2C，0x32 字节： 25 WCHARs 的数组。</span><span class="sxs-lookup"><span data-stu-id="25379-189">Offset 0x2C, 0x32 bytes: array of 25 WCHARs.</span></span> <span data-ttu-id="25379-190">一个 Unicode 零结尾字符串值:"http://www.microsoft.com"。</span><span class="sxs-lookup"><span data-stu-id="25379-190">A Unicode zero-terminated string value: "http://www.microsoft.com".</span></span>
    

