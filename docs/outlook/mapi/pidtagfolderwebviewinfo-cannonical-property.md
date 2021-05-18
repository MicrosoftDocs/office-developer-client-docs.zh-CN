---
title: PidTagFolderWebViewInfo 规范属性
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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316308"
---
# <a name="pidtagfolderwebviewinfo-cannonical-property"></a><span data-ttu-id="75d38-103">PidTagFolderWebViewInfo 规范属性</span><span class="sxs-lookup"><span data-stu-id="75d38-103">PidTagFolderWebViewInfo Cannonical Property</span></span>

  
  
<span data-ttu-id="75d38-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="75d38-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="75d38-105">包含 Microsoft 文件夹中文件夹主页的 URL Outlook。</span><span class="sxs-lookup"><span data-stu-id="75d38-105">Contains the URL for the home page of a folder in Microsoft Outlook.</span></span> <span data-ttu-id="75d38-106">此属性包含名为 **WebViewPersistenceObject 的二进制流**。</span><span class="sxs-lookup"><span data-stu-id="75d38-106">This property contains a binary stream called **WebViewPersistenceObject**.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="75d38-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="75d38-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="75d38-108">PR_FOLDER_WEBVIEWINFO</span><span class="sxs-lookup"><span data-stu-id="75d38-108">PR_FOLDER_WEBVIEWINFO</span></span>  <br/> |
|<span data-ttu-id="75d38-109">标识符:</span><span class="sxs-lookup"><span data-stu-id="75d38-109">Identifier:</span></span>  <br/> |<span data-ttu-id="75d38-110">0x36DF</span><span class="sxs-lookup"><span data-stu-id="75d38-110">0x36DF</span></span>  <br/> |
|<span data-ttu-id="75d38-111">数据类型：</span><span class="sxs-lookup"><span data-stu-id="75d38-111">Data type:</span></span>  <br/> |<span data-ttu-id="75d38-112">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="75d38-112">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="75d38-113">区域：</span><span class="sxs-lookup"><span data-stu-id="75d38-113">Area:</span></span>  <br/> |<span data-ttu-id="75d38-114">MAPI 文件夹</span><span class="sxs-lookup"><span data-stu-id="75d38-114">MAPI folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="75d38-115">备注</span><span class="sxs-lookup"><span data-stu-id="75d38-115">Remarks</span></span>

<span data-ttu-id="75d38-116">可指定任何文件夹的主页 URL Outlook URL。</span><span class="sxs-lookup"><span data-stu-id="75d38-116">A home page URL can be specified for any Outlook folder.</span></span> <span data-ttu-id="75d38-117">可以从文件夹的"Outlook"对话框的"主页"选项卡访问此信息。</span><span class="sxs-lookup"><span data-stu-id="75d38-117">This information can be accessed in Outlook from the **Home Page** tab of the Properties dialog box for a folder.</span></span> 
  
<span data-ttu-id="75d38-118">如果包含此文件夹的 MAPI 存储未在其[IMSCapabilities：：GetCapabilities](pidtagfolderwebviewinfo-cannonical-property.md)实现中报告 MSCAP_SECURE_FOLDER_HOMEPAGES，则 Outlook 可能会忽略主页，具体取决于某些策略设置。</span><span class="sxs-lookup"><span data-stu-id="75d38-118">Depending on certain policy settings, the home page might be ignored by Outlook if the MAPI store that contains this folder does not report MSCAP_SECURE_FOLDER_HOMEPAGES in its [IMSCapabilities::GetCapabilities](pidtagfolderwebviewinfo-cannonical-property.md) implementation.</span></span> 
  
<span data-ttu-id="75d38-119">The **Outlook Today** folder and a public folder can have home page URLs.</span><span class="sxs-lookup"><span data-stu-id="75d38-119">Both the **Outlook Today** folder and a public folder can have home page URLs.</span></span> <span data-ttu-id="75d38-120">但是 **，Outlook Today** 文件夹使用不同的机制来管理其主页 URL;本主题中未介绍该机制。</span><span class="sxs-lookup"><span data-stu-id="75d38-120">However the **Outlook Today** folder uses a different mechanism to manage its home page URL; that mechanism is not covered in this topic.</span></span> <span data-ttu-id="75d38-121">公用文件夹可能还有一个特定于用户的主页 URL 定义。</span><span class="sxs-lookup"><span data-stu-id="75d38-121">A public folder might also have a home page URL defined in it that is specific to a user.</span></span> <span data-ttu-id="75d38-122">但是，本主题中未介绍该功能。</span><span class="sxs-lookup"><span data-stu-id="75d38-122">However, that capability is not described in this topic.</span></span> 
  
<span data-ttu-id="75d38-123">此属性的值是一个称为 **WebViewPersistenceObject 的二进制流**。</span><span class="sxs-lookup"><span data-stu-id="75d38-123">The value of this property is a binary stream called **WebViewPersistenceObject**.</span></span>
  
### <a name="webviewpersistenceobject-stream-structure"></a><span data-ttu-id="75d38-124">WebViewPersistenceObject 流结构</span><span class="sxs-lookup"><span data-stu-id="75d38-124">WebViewPersistenceObject Stream Structure</span></span>

<span data-ttu-id="75d38-125">**WebViewPersistenceObject** 流结构包含有关文件夹的主页 URL 的信息。</span><span class="sxs-lookup"><span data-stu-id="75d38-125">The **WebViewPersistenceObject** stream structure contains information about a home page URL for a folder.</span></span> 
  
<span data-ttu-id="75d38-126">此结构中的数据元素按小尾字节顺序存储，按照以下指定顺序彼此紧接。</span><span class="sxs-lookup"><span data-stu-id="75d38-126">Data elements in this structure are stored in little-endian byte order, immediately following one another in the following specified order.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="75d38-127">以下说明可能未列出所有受此参数支持的Outlook;因此，当代码读取现有流时，也可能找到此处未列出的某些标志。</span><span class="sxs-lookup"><span data-stu-id="75d38-127">The following description may not list all of the field values supported by Outlook; therefore, when your code reads an existing stream, some flags that are not listed here might also be found.</span></span> <span data-ttu-id="75d38-128">但是，您可以使用此说明以编程方式为 **PidTagFolderWebViewInfo** 属性创建值，Outlook理解。</span><span class="sxs-lookup"><span data-stu-id="75d38-128">However, you can use this description to programmatically create values for the **PidTagFolderWebViewInfo** property that Outlook will understand.</span></span> 
  
 <span data-ttu-id="75d38-129">_dwVersion_</span><span class="sxs-lookup"><span data-stu-id="75d38-129">_dwVersion_</span></span>
  
> <span data-ttu-id="75d38-130">DWORD (4 字节) 。</span><span class="sxs-lookup"><span data-stu-id="75d38-130">DWORD (4 bytes).</span></span> <span data-ttu-id="75d38-131">结构格式的版本。</span><span class="sxs-lookup"><span data-stu-id="75d38-131">The version of the structure's format.</span></span> <span data-ttu-id="75d38-132">自 2007 Microsoft Office Outlook起，此字段的唯一受支持值如下所示。</span><span class="sxs-lookup"><span data-stu-id="75d38-132">As of Microsoft Office Outlook 2007, the only supported value for this field is as follows.</span></span>
    
|<span data-ttu-id="75d38-133">**值名称**</span><span class="sxs-lookup"><span data-stu-id="75d38-133">**Value name**</span></span>|<span data-ttu-id="75d38-134">**值**</span><span class="sxs-lookup"><span data-stu-id="75d38-134">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="75d38-135">WEBVIEW_PERSISTENCE_VERSION</span><span class="sxs-lookup"><span data-stu-id="75d38-135">WEBVIEW_PERSISTENCE_VERSION</span></span>  <br/> |<span data-ttu-id="75d38-136">0x00000002</span><span class="sxs-lookup"><span data-stu-id="75d38-136">0x00000002</span></span>  <br/> |
   
 <span data-ttu-id="75d38-137">_dwType_</span><span class="sxs-lookup"><span data-stu-id="75d38-137">_dwType_</span></span>
  
> <span data-ttu-id="75d38-138">DWORD (4 字节) 。</span><span class="sxs-lookup"><span data-stu-id="75d38-138">DWORD (4 bytes).</span></span> <span data-ttu-id="75d38-139">主页信息的类型。</span><span class="sxs-lookup"><span data-stu-id="75d38-139">The type of the home page information.</span></span> <span data-ttu-id="75d38-140">自 2007 Microsoft Office Outlook起，此字段的唯一受支持值如下所示。</span><span class="sxs-lookup"><span data-stu-id="75d38-140">As of Microsoft Office Outlook 2007, the only supported value for this field is as follows.</span></span>
    
|<span data-ttu-id="75d38-141">**值名称**</span><span class="sxs-lookup"><span data-stu-id="75d38-141">**Value name**</span></span>|<span data-ttu-id="75d38-142">**值**</span><span class="sxs-lookup"><span data-stu-id="75d38-142">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="75d38-143">WEBVIEWURL</span><span class="sxs-lookup"><span data-stu-id="75d38-143">WEBVIEWURL</span></span>  <br/> |<span data-ttu-id="75d38-144">0x00000001</span><span class="sxs-lookup"><span data-stu-id="75d38-144">0x00000001</span></span>  <br/> |
   
 <span data-ttu-id="75d38-145">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="75d38-145">_dwFlags_</span></span>
  
> <span data-ttu-id="75d38-146">DWORD (4 字节) 。</span><span class="sxs-lookup"><span data-stu-id="75d38-146">DWORD (4 bytes).</span></span> <span data-ttu-id="75d38-147">下表列出了其值和含义的零个或多个标志的组合。</span><span class="sxs-lookup"><span data-stu-id="75d38-147">A combination of zero or more flags whose values and meanings are listed in the following table.</span></span>
    
|<span data-ttu-id="75d38-148">标志名称\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="75d38-148">\*\*\*\*Flag name\*\*\*\*</span></span>|<span data-ttu-id="75d38-149">\*\*\*\*值\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="75d38-149">\*\*\*\*Value\*\*\*\*</span></span>|<span data-ttu-id="75d38-150">\*\*\*\*说明\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="75d38-150">\*\*\*\*Description\*\*\*\*</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="75d38-151">WEBVIEW_FLAGS_SHOWBYDEFAULT</span><span class="sxs-lookup"><span data-stu-id="75d38-151">WEBVIEW_FLAGS_SHOWBYDEFAULT</span></span>  <br/> |<span data-ttu-id="75d38-152">0x00000001</span><span class="sxs-lookup"><span data-stu-id="75d38-152">0x00000001</span></span>  <br/> |<span data-ttu-id="75d38-153">在 **文件夹的"属性**"对话框的"主页"选项卡中选中了"默认情况下显示此文件夹的主页"复选框。</span><span class="sxs-lookup"><span data-stu-id="75d38-153">The **Show home page by default for this folder** check box was checked in the **Home Page** tab of the Properties dialog box for a folder.</span></span>  <br/> |
   
 <span data-ttu-id="75d38-154">_dwUnused[7]_</span><span class="sxs-lookup"><span data-stu-id="75d38-154">_dwUnused[7]_</span></span>
  
> <span data-ttu-id="75d38-155">一个包含 7 个 DWORD 元素 (28 个字节) 。</span><span class="sxs-lookup"><span data-stu-id="75d38-155">An array of 7 DWORD elements (28 bytes total).</span></span> <span data-ttu-id="75d38-156">未使用。</span><span class="sxs-lookup"><span data-stu-id="75d38-156">Unused.</span></span>
    
<span data-ttu-id="75d38-157">cbData</span><span class="sxs-lookup"><span data-stu-id="75d38-157">cbData</span></span>
  
> <span data-ttu-id="75d38-158">ULONG (4 字节) 。</span><span class="sxs-lookup"><span data-stu-id="75d38-158">A ULONG (4 bytes).</span></span> <span data-ttu-id="75d38-159">_wzURL_ 数据元素的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="75d38-159">The size, in bytes, of the  _wzURL_ data element.</span></span> 
    
 <span data-ttu-id="75d38-160">_wzURL_</span><span class="sxs-lookup"><span data-stu-id="75d38-160">_wzURL_</span></span>
  
> <span data-ttu-id="75d38-161">WCHAR 元素的数组。</span><span class="sxs-lookup"><span data-stu-id="75d38-161">An array of WCHAR elements.</span></span> <span data-ttu-id="75d38-162">以零结尾的主页 URL 字符串的 UTF-16 表示形式。</span><span class="sxs-lookup"><span data-stu-id="75d38-162">The UTF-16 representation of the zero-terminated home page URL string.</span></span>
    
### <a name="webviewpersistenceobject-stream-sample"></a><span data-ttu-id="75d38-163">WebViewPersistenceObject 流示例</span><span class="sxs-lookup"><span data-stu-id="75d38-163">WebViewPersistenceObject Stream Sample</span></span>

<span data-ttu-id="75d38-164">本节介绍 **WebViewPersistenceObject 流** 的示例。</span><span class="sxs-lookup"><span data-stu-id="75d38-164">This section describes an example of a **WebViewPersistenceObject** stream.</span></span> <span data-ttu-id="75d38-165">流指定主页 URL " https://www.microsoft.com "。</span><span class="sxs-lookup"><span data-stu-id="75d38-165">The stream specifies the home page URL "https://www.microsoft.com".</span></span> 
  
 <span data-ttu-id="75d38-166">**数据转储**</span><span class="sxs-lookup"><span data-stu-id="75d38-166">**Data dump**</span></span>
  
<span data-ttu-id="75d38-167">下面是流的数据转储，就像在二进制编辑器中显示一样。</span><span class="sxs-lookup"><span data-stu-id="75d38-167">The following is a data dump of the stream as it would be displayed in a binary editor.</span></span>
  
|<span data-ttu-id="75d38-168">**流偏移**</span><span class="sxs-lookup"><span data-stu-id="75d38-168">**Stream offset**</span></span>|<span data-ttu-id="75d38-169">**数据字节数**</span><span class="sxs-lookup"><span data-stu-id="75d38-169">**Data bytes**</span></span>|<span data-ttu-id="75d38-170">**ASCII 数据**</span><span class="sxs-lookup"><span data-stu-id="75d38-170">**ASCII data**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="75d38-171">0000000000</span><span class="sxs-lookup"><span data-stu-id="75d38-171">0000000000</span></span>  <br/> | `02 00 00 00 01 00 00 00 01 00 00 00 00 00 00 00` <br/> | `?...?...?.......` <br/> |
|<span data-ttu-id="75d38-172">0000000010</span><span class="sxs-lookup"><span data-stu-id="75d38-172">0000000010</span></span>  <br/> | `00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00` <br/> | `................` <br/> |
|<span data-ttu-id="75d38-173">0000000020</span><span class="sxs-lookup"><span data-stu-id="75d38-173">0000000020</span></span>  <br/> | `00 00 00 00 00 00 00 00 32 00 00 00 68 00 74 00` <br/> | `........2...h.t.` <br/> |
|<span data-ttu-id="75d38-174">0000000030</span><span class="sxs-lookup"><span data-stu-id="75d38-174">0000000030</span></span>  <br/> | `74 00 70 00 3A 00 2F 00 2F 00 77 00 77 00 77 00` <br/> | `t.p.:././.w.w.w.` <br/> |
|<span data-ttu-id="75d38-175">0000000040</span><span class="sxs-lookup"><span data-stu-id="75d38-175">0000000040</span></span>  <br/> | `2E 00 6D 00 69 00 63 00 72 00 6F 00 73 00 6F 00` <br/> | `..m.i.c.r.o.s.o.` <br/> |
|<span data-ttu-id="75d38-176">0000000050</span><span class="sxs-lookup"><span data-stu-id="75d38-176">0000000050</span></span>  <br/> | `66 00 74 00 2E 00 63 00 6F 00 6D 00 00 00` <br/> | `f.t...c.o.m...` <br/> |
   
<span data-ttu-id="75d38-177">下面是 **WebViewPersistenceObject 流的示例数据的分析** 。</span><span class="sxs-lookup"><span data-stu-id="75d38-177">The following is a parse of the sample data for the **WebViewPersistenceObject** stream.</span></span> 
  
 <span data-ttu-id="75d38-178">_dwVersion_</span><span class="sxs-lookup"><span data-stu-id="75d38-178">_dwVersion_</span></span>
  
> <span data-ttu-id="75d38-179">偏移0x0，4 字节：0x00000002 (WEBVIEW_PERSISTENCE_VERSION) 。</span><span class="sxs-lookup"><span data-stu-id="75d38-179">Offset 0x0, 4 bytes: 0x00000002 (WEBVIEW_PERSISTENCE_VERSION).</span></span>
    
 <span data-ttu-id="75d38-180">_dwType_</span><span class="sxs-lookup"><span data-stu-id="75d38-180">_dwType_</span></span>
  
> <span data-ttu-id="75d38-181">偏移0x4，4 个字节：0x00000001 (WEBVIEWURL) 。</span><span class="sxs-lookup"><span data-stu-id="75d38-181">Offset 0x4, 4 bytes: 0x00000001 (WEBVIEWURL).</span></span>
    
 <span data-ttu-id="75d38-182">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="75d38-182">_dwFlags_</span></span>
  
> <span data-ttu-id="75d38-183">偏移0x8，4 字节：0x00000001 (WEBVIEW_FLAGS_SHOWBYDEFAULT) 。</span><span class="sxs-lookup"><span data-stu-id="75d38-183">Offset 0x8, 4 bytes: 0x00000001 (WEBVIEW_FLAGS_SHOWBYDEFAULT).</span></span>
    
 <span data-ttu-id="75d38-184">_dwUnused[7]_</span><span class="sxs-lookup"><span data-stu-id="75d38-184">_dwUnused[7]_</span></span>
  
> <span data-ttu-id="75d38-185">偏移0xC，28 个字节：全部为零。</span><span class="sxs-lookup"><span data-stu-id="75d38-185">Offset 0xC, 28 bytes: all zeros.</span></span>
    
 <span data-ttu-id="75d38-186">_cbData_</span><span class="sxs-lookup"><span data-stu-id="75d38-186">_cbData_</span></span>
  
> <span data-ttu-id="75d38-187">偏移0x28，4 字节：0x00000032。</span><span class="sxs-lookup"><span data-stu-id="75d38-187">Offset 0x28, 4 bytes: 0x00000032.</span></span>
    
 <span data-ttu-id="75d38-188">_wzURL_</span><span class="sxs-lookup"><span data-stu-id="75d38-188">_wzURL_</span></span>
  
> <span data-ttu-id="75d38-189">偏移0x2C，0x32字节：25 个 WCHAR 的数组。</span><span class="sxs-lookup"><span data-stu-id="75d38-189">Offset 0x2C, 0x32 bytes: array of 25 WCHARs.</span></span> <span data-ttu-id="75d38-190">Unicode 以零结尾的字符串值 https://www.microsoft.com ：""。</span><span class="sxs-lookup"><span data-stu-id="75d38-190">A Unicode zero-terminated string value: "https://www.microsoft.com".</span></span>
    

