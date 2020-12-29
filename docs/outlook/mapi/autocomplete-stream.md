---
title: 自动完成流
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: d4f380fa-2ed9-4c7c-9ef3-b32f8409f657
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: aadfba3e2674c35019a2e5f3eb374fbed1ad2a75
ms.sourcegitcommit: 0419850d5c1b3439d9da59070201fb4952ca5d07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/28/2020
ms.locfileid: "49734222"
---
# <a name="autocomplete-stream"></a><span data-ttu-id="38251-103">自动完成流</span><span class="sxs-lookup"><span data-stu-id="38251-103">Autocomplete Stream</span></span>

  
  
<span data-ttu-id="38251-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="38251-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="38251-105">除了知道 Microsoft Outlook 如何与自动完成流交互之外，还必须了解自动完成流的二进制格式。</span><span class="sxs-lookup"><span data-stu-id="38251-105">In addition to knowing how Microsoft Outlook interacts with the autocomplete stream, you must also understand the binary format of the autocomplete stream.</span></span>
  
<span data-ttu-id="38251-106">自动完成流是一组收件人属性行，它们与仅由 Microsoft Outlook 2013、Microsoft Outlook 2010、Microsoft Office Outlook 2007 和 Microsoft Outlook 2003 使用的一些记帐元数据一起保存为二进制流。</span><span class="sxs-lookup"><span data-stu-id="38251-106">The autocomplete stream is a set of recipient property rows that are saved as a binary stream together with some bookkeeping metadata that is used only by Microsoft Outlook 2013, Microsoft Outlook 2010, Microsoft Office Outlook 2007, and Microsoft Outlook 2003.</span></span> <span data-ttu-id="38251-107">元数据与 Outlook 与自动完成流的交互相关，因此第三方在保存修改后的自动完成流时必须保留每个元数据块中的内容。</span><span class="sxs-lookup"><span data-stu-id="38251-107">The metadata is relevant to Outlook interactions with the autocomplete stream so third parties must preserve what is in each metadata block when they save a modified autocomplete stream.</span></span> <span data-ttu-id="38251-108">换句话说，第三方应仅修改二进制格式的行集部分，并保留自动完成流的元数据块中已有的内容。</span><span class="sxs-lookup"><span data-stu-id="38251-108">In other words, third parties should modify only the row-set part of the binary format and preserve what was already in the metadata blocks of the autocomplete stream.</span></span>
  
## <a name="stream-visualization"></a><span data-ttu-id="38251-109">流可视化</span><span class="sxs-lookup"><span data-stu-id="38251-109">Stream Visualization</span></span>

<span data-ttu-id="38251-110">自动完成流高级布局如下所示：</span><span class="sxs-lookup"><span data-stu-id="38251-110">The high-level layout of the autocomplete stream is as follows:</span></span>
  
<span data-ttu-id="38251-111">元数据 (4 字节) </span><span class="sxs-lookup"><span data-stu-id="38251-111">Metadata (4 bytes)</span></span>
  
<span data-ttu-id="38251-112">主版本号 (4 字节) </span><span class="sxs-lookup"><span data-stu-id="38251-112">Major Version Number (4 bytes)</span></span>
  
<span data-ttu-id="38251-113">次要版本号 (4 字节) </span><span class="sxs-lookup"><span data-stu-id="38251-113">Minor Version Number (4 bytes)</span></span>
  
<span data-ttu-id="38251-114">行数 n (4 字节) </span><span class="sxs-lookup"><span data-stu-id="38251-114">Number of rows n (4 bytes)</span></span>
  
<span data-ttu-id="38251-115">第一行中的属性 p (4 个字节) </span><span class="sxs-lookup"><span data-stu-id="38251-115">Number of properties p in row one (4 bytes)</span></span>
  
<span data-ttu-id="38251-116">属性 1 的属性标记大小为 4 (字节) </span><span class="sxs-lookup"><span data-stu-id="38251-116">Property 1's property tag (4 bytes)</span></span>
  
<span data-ttu-id="38251-117">属性 1 的保留数据 (4 字节) </span><span class="sxs-lookup"><span data-stu-id="38251-117">Property 1's reserved data (4 bytes)</span></span>
  
<span data-ttu-id="38251-118">属性 1 的值联合 (8 字节) </span><span class="sxs-lookup"><span data-stu-id="38251-118">Property 1's value union (8 bytes)</span></span>
  
<span data-ttu-id="38251-119">属性 1 的值数据 (0 或可变字节) </span><span class="sxs-lookup"><span data-stu-id="38251-119">Property 1's value data (0 or variable bytes)</span></span>
  
<span data-ttu-id="38251-120">…</span><span class="sxs-lookup"><span data-stu-id="38251-120">…</span></span> <span data-ttu-id="38251-121"> (属性 P-1) </span><span class="sxs-lookup"><span data-stu-id="38251-121">(property 2 through property P-1)</span></span>
  
<span data-ttu-id="38251-122">属性 p 的属性标记大小为 4 (字节) </span><span class="sxs-lookup"><span data-stu-id="38251-122">Property p's property tag (4 bytes)</span></span>
  
<span data-ttu-id="38251-123">属性 p 的保留数据 (4 字节) </span><span class="sxs-lookup"><span data-stu-id="38251-123">Property p's reserved data (4 bytes)</span></span>
  
<span data-ttu-id="38251-124">属性 p 的值联合 (8 字节) </span><span class="sxs-lookup"><span data-stu-id="38251-124">Property p's value union (8 bytes)</span></span>
  
<span data-ttu-id="38251-125">属性值 p 的值数据 (0 或可变字节) </span><span class="sxs-lookup"><span data-stu-id="38251-125">Property p's value data (0 or variable bytes)</span></span>
  
<span data-ttu-id="38251-126">第二行中的属性 q 数 (4 字节) </span><span class="sxs-lookup"><span data-stu-id="38251-126">Number of properties q in row two (4 bytes)</span></span>
  
<span data-ttu-id="38251-127">…</span><span class="sxs-lookup"><span data-stu-id="38251-127">…</span></span> <span data-ttu-id="38251-128"> (第二行的属性) </span><span class="sxs-lookup"><span data-stu-id="38251-128">(row two's properties)</span></span>
  
<span data-ttu-id="38251-129">…</span><span class="sxs-lookup"><span data-stu-id="38251-129">…</span></span> <span data-ttu-id="38251-130"> (第 3 行至第 n-1 行) </span><span class="sxs-lookup"><span data-stu-id="38251-130">(row 3 through row n-1)</span></span>
  
<span data-ttu-id="38251-131">第 n 行中的属性 r (4 个字节) </span><span class="sxs-lookup"><span data-stu-id="38251-131">Number of properties r in row n (4 bytes)</span></span>
  
<span data-ttu-id="38251-132">…</span><span class="sxs-lookup"><span data-stu-id="38251-132">…</span></span> <span data-ttu-id="38251-133"> (行 n 的属性) </span><span class="sxs-lookup"><span data-stu-id="38251-133">(row n's properties)</span></span>
  
<span data-ttu-id="38251-134">额外信息字节计数 EI (4 字节) </span><span class="sxs-lookup"><span data-stu-id="38251-134">Extra information byte count EI (4 bytes)</span></span>
  
<span data-ttu-id="38251-135">有关信息 (EI 字节) </span><span class="sxs-lookup"><span data-stu-id="38251-135">Extra information (EI bytes)</span></span>
  
<span data-ttu-id="38251-136">元数据 (8 字节) </span><span class="sxs-lookup"><span data-stu-id="38251-136">Metadata (8 bytes)</span></span>
  
<span data-ttu-id="38251-137">有关二进制结构的示例，请参阅[Outlook 2003/2007 NK2](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)文件格式和开发人员指南中的二进制示例。</span><span class="sxs-lookup"><span data-stu-id="38251-137">For an example of a binary structure, see Binary Example in the [Outlook 2003/2007 NK2 File Format and Developer Guidelines.](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)</span></span>
  
## <a name="high-level-layout"></a><span data-ttu-id="38251-138">高级布局</span><span class="sxs-lookup"><span data-stu-id="38251-138">High-level Layout</span></span>

<span data-ttu-id="38251-139">一般来说，自动完成流的布局如下所示：</span><span class="sxs-lookup"><span data-stu-id="38251-139">Broadly speaking, the layout of the autocomplete stream is as follows:</span></span>
  
|<span data-ttu-id="38251-140">**数值数据**</span><span class="sxs-lookup"><span data-stu-id="38251-140">**Value Data**</span></span>|<span data-ttu-id="38251-141">**字节数**</span><span class="sxs-lookup"><span data-stu-id="38251-141">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38251-142">Metadata</span><span class="sxs-lookup"><span data-stu-id="38251-142">Metadata</span></span>  <br/> |<span data-ttu-id="38251-143">4 </span><span class="sxs-lookup"><span data-stu-id="38251-143">4</span></span>  <br/> |
|<span data-ttu-id="38251-144">主要版本号</span><span class="sxs-lookup"><span data-stu-id="38251-144">Major Version Number</span></span>  <br/> |<span data-ttu-id="38251-145">4 </span><span class="sxs-lookup"><span data-stu-id="38251-145">4</span></span>  <br/> |
|<span data-ttu-id="38251-146">次要版本号</span><span class="sxs-lookup"><span data-stu-id="38251-146">Minor Version Number</span></span>  <br/> |<span data-ttu-id="38251-147">4 </span><span class="sxs-lookup"><span data-stu-id="38251-147">4</span></span>  <br/> |
|<span data-ttu-id="38251-148">行集</span><span class="sxs-lookup"><span data-stu-id="38251-148">Row-set</span></span>  <br/> |<span data-ttu-id="38251-149">变量</span><span class="sxs-lookup"><span data-stu-id="38251-149">Variable</span></span>  <br/> |
|<span data-ttu-id="38251-150">额外信息字节计数 EI</span><span class="sxs-lookup"><span data-stu-id="38251-150">Extra information byte count EI</span></span>  <br/> |<span data-ttu-id="38251-151">4 </span><span class="sxs-lookup"><span data-stu-id="38251-151">4</span></span>  <br/> |
|<span data-ttu-id="38251-152">额外信息</span><span class="sxs-lookup"><span data-stu-id="38251-152">Extra information</span></span>  <br/> |<span data-ttu-id="38251-153">EI</span><span class="sxs-lookup"><span data-stu-id="38251-153">EI</span></span>  <br/> |
|<span data-ttu-id="38251-154">Metadata</span><span class="sxs-lookup"><span data-stu-id="38251-154">Metadata</span></span>  <br/> |<span data-ttu-id="38251-155">8 </span><span class="sxs-lookup"><span data-stu-id="38251-155">8</span></span>  <br/> |
   
<span data-ttu-id="38251-156">读取此流时，如果主要版本不同于 12，则不应读取或写入此流。</span><span class="sxs-lookup"><span data-stu-id="38251-156">When reading this stream, if the major version is different than 12, then this stream should not be read or written.</span></span> <span data-ttu-id="38251-157">自动完成流的当前次要版本为 0，其中额外信息字节计数设置为 0。</span><span class="sxs-lookup"><span data-stu-id="38251-157">The current minor version of the autocomplete stream is 0, which has the Extra Information Byte count set to 0.</span></span> <span data-ttu-id="38251-158">如果次要版本不同于 0，则读取流时需要读取的额外信息中会包含一些信息，在编写流时需要保留这些信息。</span><span class="sxs-lookup"><span data-stu-id="38251-158">If the minor version is different than 0, then there will be information in the extra information that needs to be read when reading the stream and preserved when writing the stream.</span></span> <span data-ttu-id="38251-159">编写流时还需要保留次要版本。</span><span class="sxs-lookup"><span data-stu-id="38251-159">The minor version will also need to be preserved when writing the stream.</span></span> <span data-ttu-id="38251-160">如果未保留这两者，则撰写额外信息的 Outlook 实例将丢失数据。</span><span class="sxs-lookup"><span data-stu-id="38251-160">If both of these are not preserved, instances of Outlook that wrote the extra information will lose data.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="38251-161">应用程序不得向"额外信息"字段添加自定义数据或更改次要版本，因为此功能是支持 Outlook 格式扩展，而不是任意第三方扩展。</span><span class="sxs-lookup"><span data-stu-id="38251-161">Applications must not add custom data to the Extra Information field or change the minor version as this functionality is to support Outlook extensions to the format and not arbitrary third-party extensions.</span></span> 
  
## <a name="row-set-layout"></a><span data-ttu-id="38251-162">行集布局</span><span class="sxs-lookup"><span data-stu-id="38251-162">Row-set Layout</span></span>

<span data-ttu-id="38251-163">行集布局如下所示：</span><span class="sxs-lookup"><span data-stu-id="38251-163">The row-set layout is as follows:</span></span> 
  
|<span data-ttu-id="38251-164">**数值数据**</span><span class="sxs-lookup"><span data-stu-id="38251-164">**Value Data**</span></span>|<span data-ttu-id="38251-165">**字节数**</span><span class="sxs-lookup"><span data-stu-id="38251-165">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38251-166">行数</span><span class="sxs-lookup"><span data-stu-id="38251-166">Number of rows</span></span>  <br/> |<span data-ttu-id="38251-167">4 </span><span class="sxs-lookup"><span data-stu-id="38251-167">4</span></span>  <br/> |
|<span data-ttu-id="38251-168">Rows</span><span class="sxs-lookup"><span data-stu-id="38251-168">Rows</span></span>  <br/> |<span data-ttu-id="38251-169">变量</span><span class="sxs-lookup"><span data-stu-id="38251-169">Variable</span></span>  <br/> |
   
<span data-ttu-id="38251-170">行数标识二进制流序列的下一部分中的行数。</span><span class="sxs-lookup"><span data-stu-id="38251-170">The number of rows identifies how many rows come in the next part of the binary stream sequence.</span></span>
  
## <a name="row-layout"></a><span data-ttu-id="38251-171">行布局</span><span class="sxs-lookup"><span data-stu-id="38251-171">Row Layout</span></span>

<span data-ttu-id="38251-172">每行的格式如下：</span><span class="sxs-lookup"><span data-stu-id="38251-172">Each row is of the following format:</span></span>
  
|<span data-ttu-id="38251-173">**数值数据**</span><span class="sxs-lookup"><span data-stu-id="38251-173">**Value Data**</span></span>|<span data-ttu-id="38251-174">**字节数**</span><span class="sxs-lookup"><span data-stu-id="38251-174">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38251-175">属性数</span><span class="sxs-lookup"><span data-stu-id="38251-175">Number of properties</span></span>  <br/> |<span data-ttu-id="38251-176">4 </span><span class="sxs-lookup"><span data-stu-id="38251-176">4</span></span>  <br/> |
|<span data-ttu-id="38251-177">属性</span><span class="sxs-lookup"><span data-stu-id="38251-177">Properties</span></span>  <br/> |<span data-ttu-id="38251-178">变量</span><span class="sxs-lookup"><span data-stu-id="38251-178">Variable</span></span>  <br/> |
   
<span data-ttu-id="38251-179">属性数标识二进制流序列的下一部分中的属性数。</span><span class="sxs-lookup"><span data-stu-id="38251-179">The number of properties identifies how many properties come in the next part of the binary stream sequence.</span></span>
  
## <a name="property-layout"></a><span data-ttu-id="38251-180">属性布局</span><span class="sxs-lookup"><span data-stu-id="38251-180">Property Layout</span></span>

<span data-ttu-id="38251-181">每个属性的格式如下：</span><span class="sxs-lookup"><span data-stu-id="38251-181">Each property is of the following format:</span></span>
  
|<span data-ttu-id="38251-182">**数值数据**</span><span class="sxs-lookup"><span data-stu-id="38251-182">**Value Data**</span></span>|<span data-ttu-id="38251-183">**字节数**</span><span class="sxs-lookup"><span data-stu-id="38251-183">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38251-184">属性标记</span><span class="sxs-lookup"><span data-stu-id="38251-184">Property Tag</span></span>  <br/> |<span data-ttu-id="38251-185">4 </span><span class="sxs-lookup"><span data-stu-id="38251-185">4</span></span>  <br/> |
|<span data-ttu-id="38251-186">保留数据</span><span class="sxs-lookup"><span data-stu-id="38251-186">Reserved Data</span></span>  <br/> |<span data-ttu-id="38251-187">4 </span><span class="sxs-lookup"><span data-stu-id="38251-187">4</span></span>  <br/> |
|<span data-ttu-id="38251-188">属性值联合</span><span class="sxs-lookup"><span data-stu-id="38251-188">Property Value Union</span></span>  <br/> ||
|<span data-ttu-id="38251-189">数值数据</span><span class="sxs-lookup"><span data-stu-id="38251-189">Value Data</span></span>  <br/> |<span data-ttu-id="38251-190">0 或变量 (取决于属性标记) </span><span class="sxs-lookup"><span data-stu-id="38251-190">0 or variable (depending on the prop tag)</span></span>  <br/> |
   
## <a name="interpreting-the-property-value"></a><span data-ttu-id="38251-191">解释属性值</span><span class="sxs-lookup"><span data-stu-id="38251-191">Interpreting the Property Value</span></span>

<span data-ttu-id="38251-192">属性值联合值和值数据根据属性块前 4 个字节中的属性标记进行解释。</span><span class="sxs-lookup"><span data-stu-id="38251-192">The Property Value Union and the Value Data are to be interpreted based on the property tag in the first 4 bytes of the property block.</span></span> <span data-ttu-id="38251-193">此属性标记的格式与 MAPI 属性标记的格式相同。</span><span class="sxs-lookup"><span data-stu-id="38251-193">This property tag is in the same format as a MAPI property tag.</span></span> <span data-ttu-id="38251-194">属性标记的位 0 到 15 是属性的类型。</span><span class="sxs-lookup"><span data-stu-id="38251-194">Bits 0 through 15 of the property tag are the property's type.</span></span> <span data-ttu-id="38251-195">位 16 到 31 是属性的标识符。</span><span class="sxs-lookup"><span data-stu-id="38251-195">Bits 16 through 31 are the property's identifier.</span></span> <span data-ttu-id="38251-196">属性类型确定属性的其余部分的读取方法。</span><span class="sxs-lookup"><span data-stu-id="38251-196">The property type determines how the rest of the property should be read.</span></span>
  
## <a name="static-value"></a><span data-ttu-id="38251-197">静态值</span><span class="sxs-lookup"><span data-stu-id="38251-197">Static Value</span></span>

<span data-ttu-id="38251-198">某些属性没有值数据，并且只有联合数据。</span><span class="sxs-lookup"><span data-stu-id="38251-198">Some properties have no Value Data and only have data in the union.</span></span> <span data-ttu-id="38251-199">以下属性类型 (属性标记) 应按如下方式解释 8 字节 Property Union 数据：</span><span class="sxs-lookup"><span data-stu-id="38251-199">The following property types (which come from the Property Tag) should interpret the 8-byte Property Union data as follows:</span></span>
  
|<span data-ttu-id="38251-200">**属性类型**</span><span class="sxs-lookup"><span data-stu-id="38251-200">**Prop Type**</span></span>|<span data-ttu-id="38251-201">**Property Union Interpretation**</span><span class="sxs-lookup"><span data-stu-id="38251-201">**Property Union Interpretation**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38251-202">PT_I2</span><span class="sxs-lookup"><span data-stu-id="38251-202">PT_I2</span></span>  <br/> |<span data-ttu-id="38251-203">short int</span><span class="sxs-lookup"><span data-stu-id="38251-203">short int</span></span>  <br/> |
|<span data-ttu-id="38251-204">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="38251-204">PT_LONG</span></span>  <br/> |<span data-ttu-id="38251-205">long</span><span class="sxs-lookup"><span data-stu-id="38251-205">long</span></span>  <br/> |
|<span data-ttu-id="38251-206">PT_ERROR</span><span class="sxs-lookup"><span data-stu-id="38251-206">PT_ERROR</span></span>  <br/> |<span data-ttu-id="38251-207">long</span><span class="sxs-lookup"><span data-stu-id="38251-207">long</span></span>  <br/> |
|<span data-ttu-id="38251-208">PT_R4</span><span class="sxs-lookup"><span data-stu-id="38251-208">PT_R4</span></span>  <br/> |<span data-ttu-id="38251-209">float</span><span class="sxs-lookup"><span data-stu-id="38251-209">float</span></span>  <br/> |
|<span data-ttu-id="38251-210">PT_DOUBLE</span><span class="sxs-lookup"><span data-stu-id="38251-210">PT_DOUBLE</span></span>  <br/> |<span data-ttu-id="38251-211">double</span><span class="sxs-lookup"><span data-stu-id="38251-211">double</span></span>  <br/> |
|<span data-ttu-id="38251-212">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="38251-212">PT_BOOLEAN</span></span>  <br/> |<span data-ttu-id="38251-213">short int</span><span class="sxs-lookup"><span data-stu-id="38251-213">short int</span></span>  <br/> |
|<span data-ttu-id="38251-214">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="38251-214">PT_SYSTIME</span></span>  <br/> |<span data-ttu-id="38251-215">FILETIME</span><span class="sxs-lookup"><span data-stu-id="38251-215">FILETIME</span></span>  <br/> |
|<span data-ttu-id="38251-216">PT_I8</span><span class="sxs-lookup"><span data-stu-id="38251-216">PT_I8</span></span>  <br/> |<span data-ttu-id="38251-217">LARGE_INTEGER</span><span class="sxs-lookup"><span data-stu-id="38251-217">LARGE_INTEGER</span></span>  <br/> |
   
## <a name="dynamic-values"></a><span data-ttu-id="38251-218">动态值</span><span class="sxs-lookup"><span data-stu-id="38251-218">Dynamic Values</span></span>

<span data-ttu-id="38251-219">其他属性在值数据块中包含 Property Tag、保留数据和属性值联合的前 16 个字节之后的数据。</span><span class="sxs-lookup"><span data-stu-id="38251-219">Other properties have data in a Value Data block after the first 16 bytes that contain the Property Tag, the Reserved Data, and the Property Value Union.</span></span> <span data-ttu-id="38251-220">与静态值不同，存储在 8 字节属性值联合中的数据与读取无关。</span><span class="sxs-lookup"><span data-stu-id="38251-220">Unlike static values, the data that is stored in the 8-byte Property Value union is irrelevant on reading.</span></span> <span data-ttu-id="38251-221">在编写时，请确保用某些内容填充这 8 个字节。</span><span class="sxs-lookup"><span data-stu-id="38251-221">When writing, make sure that you fill these 8 bytes with something.</span></span> <span data-ttu-id="38251-222">但是，8 字节的内容并不重要。</span><span class="sxs-lookup"><span data-stu-id="38251-222">However, the content of the 8 bytes is not important.</span></span> <span data-ttu-id="38251-223">在动态值中，属性标记的类型确定如何解释值数据。</span><span class="sxs-lookup"><span data-stu-id="38251-223">In dynamic values, the property tag's type determines how to interpret the Value Data.</span></span>
  
<span data-ttu-id="38251-224">PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="38251-224">PT_STRING8</span></span> 
  
|<span data-ttu-id="38251-225">**数值数据**</span><span class="sxs-lookup"><span data-stu-id="38251-225">**Value Data**</span></span>|<span data-ttu-id="38251-226">**字节数**</span><span class="sxs-lookup"><span data-stu-id="38251-226">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38251-227">字节数 n</span><span class="sxs-lookup"><span data-stu-id="38251-227">Number of bytes n</span></span>  <br/> |<span data-ttu-id="38251-228">4 </span><span class="sxs-lookup"><span data-stu-id="38251-228">4</span></span>  <br/> |
|<span data-ttu-id="38251-229">要解释为 ANSI 字符串字符串的 (包括 NULL 终止符) </span><span class="sxs-lookup"><span data-stu-id="38251-229">Bytes to be interpreted as an ANSI string (includes NULL terminator)</span></span>  <br/> |<span data-ttu-id="38251-230">n</span><span class="sxs-lookup"><span data-stu-id="38251-230">n</span></span>  <br/> |
   
<span data-ttu-id="38251-231">PT_CLSID</span><span class="sxs-lookup"><span data-stu-id="38251-231">PT_CLSID</span></span>
  
|<span data-ttu-id="38251-232">**数值数据**</span><span class="sxs-lookup"><span data-stu-id="38251-232">**Value Data**</span></span>|<span data-ttu-id="38251-233">**字节数**</span><span class="sxs-lookup"><span data-stu-id="38251-233">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38251-234">要解释为 GUID 的字节数</span><span class="sxs-lookup"><span data-stu-id="38251-234">Bytes to be interpreted as a GUID</span></span>  <br/> |<span data-ttu-id="38251-235">16 </span><span class="sxs-lookup"><span data-stu-id="38251-235">16</span></span>  <br/> |
|||
   
<span data-ttu-id="38251-236">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="38251-236">PT_BINARY</span></span> 
  
|<span data-ttu-id="38251-237">**数值数据**</span><span class="sxs-lookup"><span data-stu-id="38251-237">**Value Data**</span></span>|<span data-ttu-id="38251-238">**字节数**</span><span class="sxs-lookup"><span data-stu-id="38251-238">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38251-239">字节数 n</span><span class="sxs-lookup"><span data-stu-id="38251-239">Number of bytes n</span></span>  <br/> |<span data-ttu-id="38251-240">4 </span><span class="sxs-lookup"><span data-stu-id="38251-240">4</span></span>  <br/> |
|<span data-ttu-id="38251-241">要解释为字节数组的字节数</span><span class="sxs-lookup"><span data-stu-id="38251-241">Bytes to be interpreted as a byte array</span></span>  <br/> |<span data-ttu-id="38251-242">n</span><span class="sxs-lookup"><span data-stu-id="38251-242">n</span></span>  <br/> |
   
<span data-ttu-id="38251-243">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="38251-243">PT_MV_BINARY</span></span>
  
|<span data-ttu-id="38251-244">**数值数据**</span><span class="sxs-lookup"><span data-stu-id="38251-244">**Value Data**</span></span>|<span data-ttu-id="38251-245">**字节数**</span><span class="sxs-lookup"><span data-stu-id="38251-245">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38251-246">二进制数组 X 的数量</span><span class="sxs-lookup"><span data-stu-id="38251-246">Number of binary arrays X</span></span>  <br/> |<span data-ttu-id="38251-247">4 </span><span class="sxs-lookup"><span data-stu-id="38251-247">4</span></span>  <br/> |
|<span data-ttu-id="38251-248">包含 X 二进制数组的字节数。</span><span class="sxs-lookup"><span data-stu-id="38251-248">A run of bytes that contains X binary arrays.</span></span> <span data-ttu-id="38251-249">每个数组应完全像字节PT_BINARY一样解释。</span><span class="sxs-lookup"><span data-stu-id="38251-249">Each array should be interpreted exactly like the PT_BINARY byte run.</span></span>  <br/> |<span data-ttu-id="38251-250">变量</span><span class="sxs-lookup"><span data-stu-id="38251-250">Variable</span></span>  <br/> |
   
<span data-ttu-id="38251-251">PT_MV_STRING8 (Outlook 2007、Outlook 2010 和 Outlook 2013) </span><span class="sxs-lookup"><span data-stu-id="38251-251">PT_MV_STRING8 (Outlook 2007, Outlook 2010, and Outlook 2013)</span></span>
  
|<span data-ttu-id="38251-252">**数值数据**</span><span class="sxs-lookup"><span data-stu-id="38251-252">**Value Data**</span></span>|<span data-ttu-id="38251-253">**字节数**</span><span class="sxs-lookup"><span data-stu-id="38251-253">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38251-254">ANSI 字符串 X 的数量</span><span class="sxs-lookup"><span data-stu-id="38251-254">Number of ANSI strings X</span></span>  <br/> |<span data-ttu-id="38251-255">4 </span><span class="sxs-lookup"><span data-stu-id="38251-255">4</span></span>  <br/> |
|<span data-ttu-id="38251-256">包含 X ANSI 字符串的字节数。</span><span class="sxs-lookup"><span data-stu-id="38251-256">A run of bytes that contains X ANSI strings.</span></span> <span data-ttu-id="38251-257">每个字符串应完全像字节PT_STRING8一样解释。</span><span class="sxs-lookup"><span data-stu-id="38251-257">Each string should be interpreted exactly like the PT_STRING8 byte run.</span></span>  <br/> |<span data-ttu-id="38251-258">变量</span><span class="sxs-lookup"><span data-stu-id="38251-258">Variable</span></span>  <br/> |
   
<span data-ttu-id="38251-259">PT_MV_UNICODE (Outlook 2007、Outlook 2010、Outlook 2013) </span><span class="sxs-lookup"><span data-stu-id="38251-259">PT_MV_UNICODE (Outlook 2007, Outlook 2010, Outlook 2013)</span></span>
  
|<span data-ttu-id="38251-260">**数值数据**</span><span class="sxs-lookup"><span data-stu-id="38251-260">**Value Data**</span></span>|<span data-ttu-id="38251-261">**字节数**</span><span class="sxs-lookup"><span data-stu-id="38251-261">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38251-262">UNICODE 字符串 X 的数量</span><span class="sxs-lookup"><span data-stu-id="38251-262">Number of UNICODE strings X</span></span>  <br/> |<span data-ttu-id="38251-263">4 </span><span class="sxs-lookup"><span data-stu-id="38251-263">4</span></span>  <br/> |
|<span data-ttu-id="38251-264">包含 X UNICODE 字符串的字节数。</span><span class="sxs-lookup"><span data-stu-id="38251-264">A run of bytes that contains X UNICODE strings.</span></span> <span data-ttu-id="38251-265">每个字符串应完全像字节PT_UNICODE一样解释。</span><span class="sxs-lookup"><span data-stu-id="38251-265">Each string should be interpreted exactly like the PT_UNICODE byte run.</span></span>  <br/> |<span data-ttu-id="38251-266">变量</span><span class="sxs-lookup"><span data-stu-id="38251-266">Variable</span></span>  <br/> |
   
## <a name="significant-properties"></a><span data-ttu-id="38251-267">重要属性</span><span class="sxs-lookup"><span data-stu-id="38251-267">Significant properties</span></span>

<span data-ttu-id="38251-268">如本主题前面所述，表示属性的二进制块具有与通讯簿收件人的属性对应的属性标记。</span><span class="sxs-lookup"><span data-stu-id="38251-268">As mentioned previously in this topic, the binary blocks that represent properties have property tags that correspond to properties on address book recipients.</span></span> <span data-ttu-id="38251-269">对于此处未列出的属性，可在以下网站查找属性说明 https://msdn.microsoft.com/library/cc433490(EXCHG.80).aspx 。</span><span class="sxs-lookup"><span data-stu-id="38251-269">For properties that are not listed here, you can look up the property description at https://msdn.microsoft.com/library/cc433490(EXCHG.80).aspx.</span></span>
  
|<span data-ttu-id="38251-270">**属性名**</span><span class="sxs-lookup"><span data-stu-id="38251-270">**Property Name**</span></span>|<span data-ttu-id="38251-271">**属性标记**</span><span class="sxs-lookup"><span data-stu-id="38251-271">**Property Tag**</span></span>|<span data-ttu-id="38251-272">**说明 (有关详细信息，请参阅 MSDN)**</span><span class="sxs-lookup"><span data-stu-id="38251-272">**Description (see MSDN for more information)**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="38251-273">PR_NICK_NAME_W (传输给收件人，特定于仅自动完成流) </span><span class="sxs-lookup"><span data-stu-id="38251-273">PR_NICK_NAME_W (not transmitted on recipients, specific to autocomplete stream only)</span></span>  <br/> |<span data-ttu-id="38251-274">0x6001001f</span><span class="sxs-lookup"><span data-stu-id="38251-274">0x6001001f</span></span>  <br/> |<span data-ttu-id="38251-275">此属性必须在每个收件人行中第一个。</span><span class="sxs-lookup"><span data-stu-id="38251-275">This property must be first in each recipient row.</span></span> <span data-ttu-id="38251-276">它在功能上充当收件人行的键标识符。</span><span class="sxs-lookup"><span data-stu-id="38251-276">It functionally serves as a key identifier for the recipient row.</span></span>  <br/> |
|<span data-ttu-id="38251-277">PR_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="38251-277">PR_ENTRYID</span></span>  <br/> |<span data-ttu-id="38251-278">0x0FFF0102</span><span class="sxs-lookup"><span data-stu-id="38251-278">0x0FFF0102</span></span>  <br/> |<span data-ttu-id="38251-279">收件人的通讯簿条目标识符。</span><span class="sxs-lookup"><span data-stu-id="38251-279">The address book entry identifier for the recipient.</span></span>  <br/> |
|<span data-ttu-id="38251-280">PR_DISPLAY_NAME_W</span><span class="sxs-lookup"><span data-stu-id="38251-280">PR_DISPLAY_NAME_W</span></span>  <br/> |<span data-ttu-id="38251-281">0x3001001F</span><span class="sxs-lookup"><span data-stu-id="38251-281">0x3001001F</span></span>  <br/> |<span data-ttu-id="38251-282">收件人的显示名称。</span><span class="sxs-lookup"><span data-stu-id="38251-282">The recipient's display name.</span></span>  <br/> |
|<span data-ttu-id="38251-283">PR_EMAIL_ADDRESS_W</span><span class="sxs-lookup"><span data-stu-id="38251-283">PR_EMAIL_ADDRESS_W</span></span>  <br/> |<span data-ttu-id="38251-284">0x3003001F</span><span class="sxs-lookup"><span data-stu-id="38251-284">0x3003001F</span></span>  <br/> |<span data-ttu-id="38251-285">收件人的电子邮件地址，例如 johndoe@contoso.com (或 /o=Contoso/OU=Foo/cn=Recipients/cn=johndoe) </span><span class="sxs-lookup"><span data-stu-id="38251-285">The recipient's email address (e.g. johndoe@contoso.com or /o=Contoso/OU=Foo/cn=Recipients/cn=johndoe)</span></span>  <br/> |
|<span data-ttu-id="38251-286">PR_ADDRTYPE_W</span><span class="sxs-lookup"><span data-stu-id="38251-286">PR_ADDRTYPE_W</span></span>  <br/> |<span data-ttu-id="38251-287">0x3002001F</span><span class="sxs-lookup"><span data-stu-id="38251-287">0x3002001F</span></span>  <br/> |<span data-ttu-id="38251-288">收件人的地址类型 (例如 SMTP 或 EX) 。</span><span class="sxs-lookup"><span data-stu-id="38251-288">The recipient's address type (e.g. SMTP or EX).</span></span>  <br/> |
|<span data-ttu-id="38251-289">PR_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="38251-289">PR_SEARCH_KEY</span></span>  <br/> |<span data-ttu-id="38251-290">0x300B0102</span><span class="sxs-lookup"><span data-stu-id="38251-290">0x300B0102</span></span>  <br/> |<span data-ttu-id="38251-291">收件人的 MAPI 搜索密钥。</span><span class="sxs-lookup"><span data-stu-id="38251-291">The recipient's MAPI search key.</span></span>  <br/> |
|<span data-ttu-id="38251-292">PR_SMTP_ADDRESS_W</span><span class="sxs-lookup"><span data-stu-id="38251-292">PR_SMTP_ADDRESS_W</span></span>  <br/> |<span data-ttu-id="38251-293">0x39FE001f</span><span class="sxs-lookup"><span data-stu-id="38251-293">0x39FE001f</span></span>  <br/> |<span data-ttu-id="38251-294">收件人的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="38251-294">The recipient's SMTP address.</span></span>  <br/> |
|<span data-ttu-id="38251-295">PR_DROPDOWN_DISPLAY_NAME_W (传输给收件人，特定于仅自动完成流) </span><span class="sxs-lookup"><span data-stu-id="38251-295">PR_DROPDOWN_DISPLAY_NAME_W (not transmitted on recipients, specific to autocomplete stream only)</span></span>  <br/> |<span data-ttu-id="38251-296">0X6003001f</span><span class="sxs-lookup"><span data-stu-id="38251-296">0X6003001f</span></span>  <br/> |<span data-ttu-id="38251-297">自动完成列表中显示的显示字符串。</span><span class="sxs-lookup"><span data-stu-id="38251-297">The display string that appears in the autocomplete list.</span></span>  <br/> |
|<span data-ttu-id="38251-298">PR_NICK_NAME_WEIGHT (传输给收件人，特定于仅自动完成流) </span><span class="sxs-lookup"><span data-stu-id="38251-298">PR_NICK_NAME_WEIGHT (not transmitted on recipients, specific to autocomplete stream only)</span></span>  <br/> |<span data-ttu-id="38251-299">0x60040003</span><span class="sxs-lookup"><span data-stu-id="38251-299">0x60040003</span></span>  <br/> |<span data-ttu-id="38251-300">此自动完成条目的权重。</span><span class="sxs-lookup"><span data-stu-id="38251-300">The weight of this autocomplete entry.</span></span> <span data-ttu-id="38251-301">权重用于确定在匹配自动完成列表时自动完成条目发生的顺序。</span><span class="sxs-lookup"><span data-stu-id="38251-301">The weight is used to determine in what order autocomplete entries occur when matching the autocomplete list.</span></span> <span data-ttu-id="38251-302">权重较高的条目显示在权重较低的条目之前。</span><span class="sxs-lookup"><span data-stu-id="38251-302">Entries with higher weight will show before entries with lower weight.</span></span> <span data-ttu-id="38251-303">完整的自动完成列表按此属性排序。</span><span class="sxs-lookup"><span data-stu-id="38251-303">The complete autocomplete list is sorted by this property.</span></span> <span data-ttu-id="38251-304">权重会随着时间的推移而定期减小，并且当用户向此收件人发送电子邮件时会增加。</span><span class="sxs-lookup"><span data-stu-id="38251-304">The weight periodically decreases over time and increases when the user sends an email to this recipient.</span></span> <span data-ttu-id="38251-305">有关此属性的详细信息，请参阅本主题稍后的说明。</span><span class="sxs-lookup"><span data-stu-id="38251-305">See the description later in this topic for more information about this property.</span></span>  <br/> |
   
<span data-ttu-id="38251-306">PR_NICK_NAME_WEIGHT</span><span class="sxs-lookup"><span data-stu-id="38251-306">PR_NICK_NAME_WEIGHT</span></span>
  
<span data-ttu-id="38251-307">自动完成流中的行集按 PR_NICK_NAME_WEIGHT 属性的降序排序，自动完成流应始终保留此排序特征。</span><span class="sxs-lookup"><span data-stu-id="38251-307">The set of rows in the autocomplete stream is sorted in descending order by the PR_NICK_NAME_WEIGHT property and the autocomplete stream should always preserve this sorted characteristic.</span></span> <span data-ttu-id="38251-308">因此，对行的权重的任何更改还应确保行的位置保持整组行的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="38251-308">Therefore, any changes to a row's weight should also ensure that the row's position maintains the sorted order of the complete set of rows.</span></span> <span data-ttu-id="38251-309">行集的任何添加内容都应插入到正确的位置以保持排序顺序。</span><span class="sxs-lookup"><span data-stu-id="38251-309">Any additions to the row-set should be inserted to the correct position to maintain the sorted order.</span></span>
  
<span data-ttu-id="38251-310">此权重的最小值为 0x1，最大值为 LONG_MAX。</span><span class="sxs-lookup"><span data-stu-id="38251-310">The minimum value of this weight is 0x1 and the maximum value is LONG_MAX.</span></span> <span data-ttu-id="38251-311">权重的其他任何值都被视为无效。</span><span class="sxs-lookup"><span data-stu-id="38251-311">Any other values for the weight are considered invalid.</span></span>
  
<span data-ttu-id="38251-312">当 Outlook 2007 向收件人发送邮件或解析收件人时，该收件人的权重将增加 0x2000。</span><span class="sxs-lookup"><span data-stu-id="38251-312">When Outlook 2007 sends a mail to or resolves a recipient, it will increase that recipient's weight by 0x2000.</span></span>
  

