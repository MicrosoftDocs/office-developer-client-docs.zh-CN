---
title: 自动完成流
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: d4f380fa-2ed9-4c7c-9ef3-b32f8409f657
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8b5c5fee71db0fc7bdd6e01c58e9c9a9c3d9fa22
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384645"
---
# <a name="autocomplete-stream"></a><span data-ttu-id="ee101-103">自动完成流</span><span class="sxs-lookup"><span data-stu-id="ee101-103">Autocomplete Stream</span></span>

  
  
<span data-ttu-id="ee101-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ee101-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ee101-105">除了知道 Microsoft Outlook 如何与自动完成流交互之外，还必须了解自动完成流的二进制格式。</span><span class="sxs-lookup"><span data-stu-id="ee101-105">In addition to knowing how Microsoft Outlook interacts with the autocomplete stream, you must also understand the binary format of the autocomplete stream.</span></span>
  
<span data-ttu-id="ee101-106">自动完成流是一组收件人属性行，它们与仅由 Microsoft Outlook 2013、Microsoft Outlook 2010、Microsoft Office Outlook 2007 和 Microsoft Outlook 2003 使用的一些记帐元数据一起保存为二进制流。</span><span class="sxs-lookup"><span data-stu-id="ee101-106">The autocomplete stream is a set of recipient property rows that are saved as a binary stream together with some bookkeeping metadata that is used only by Microsoft Outlook 2013, Microsoft Outlook 2010, Microsoft Office Outlook 2007, and Microsoft Outlook 2003.</span></span> <span data-ttu-id="ee101-107">元数据与 Outlook 与自动完成流的交互相关，因此第三方在保存修改后的自动完成流时必须保留每个元数据块中的内容。</span><span class="sxs-lookup"><span data-stu-id="ee101-107">The metadata is relevant to Outlook interactions with the autocomplete stream so third parties must preserve what is in each metadata block when they save a modified autocomplete stream.</span></span> <span data-ttu-id="ee101-108">换句话说，第三方应仅修改二进制格式的行集部分，并保留自动完成流的元数据块中已有的内容。</span><span class="sxs-lookup"><span data-stu-id="ee101-108">In other words, third parties should modify only the row-set part of the binary format and preserve what was already in the metadata blocks of the autocomplete stream.</span></span>
  
## <a name="stream-visualization"></a><span data-ttu-id="ee101-109">数据流可视化</span><span class="sxs-lookup"><span data-stu-id="ee101-109">Stream Visualization</span></span>

<span data-ttu-id="ee101-110">自动完成流的高级别布局如下所示：</span><span class="sxs-lookup"><span data-stu-id="ee101-110">The high-level layout of the autocomplete stream is as follows:</span></span>
  
<span data-ttu-id="ee101-111">元数据（4 个字节）</span><span class="sxs-lookup"><span data-stu-id="ee101-111">Metadata (4 bytes)</span></span>
  
<span data-ttu-id="ee101-112">主要版本号（4 个字节）</span><span class="sxs-lookup"><span data-stu-id="ee101-112">Major Version Number (4 bytes)</span></span>
  
<span data-ttu-id="ee101-113">次要版本号（4 个字节）</span><span class="sxs-lookup"><span data-stu-id="ee101-113">Minor Version Number (4 bytes)</span></span>
  
<span data-ttu-id="ee101-114">行 n 的数量（4 个字节）</span><span class="sxs-lookup"><span data-stu-id="ee101-114">Number of rows n (4 bytes)</span></span>
  
<span data-ttu-id="ee101-115">行 1 中属性 p 的数量（4 个字节）</span><span class="sxs-lookup"><span data-stu-id="ee101-115">Number of properties p in row one (4 bytes)</span></span>
  
<span data-ttu-id="ee101-116">属性 1 的属性标记（4 个字节）</span><span class="sxs-lookup"><span data-stu-id="ee101-116">Property 1's property tag (4 bytes)</span></span>
  
<span data-ttu-id="ee101-117">属性 1 的保留数据（4 个字节）</span><span class="sxs-lookup"><span data-stu-id="ee101-117">Property 1's reserved data (4 bytes)</span></span>
  
<span data-ttu-id="ee101-118">属性 1 的值联合（8 个字节）</span><span class="sxs-lookup"><span data-stu-id="ee101-118">Property 1's value union (8 bytes)</span></span>
  
<span data-ttu-id="ee101-119">属性 1 的值数据（0 个或变量字节）</span><span class="sxs-lookup"><span data-stu-id="ee101-119">Property 1's value data (0 or variable bytes)</span></span>
  
<span data-ttu-id="ee101-120">…</span><span class="sxs-lookup"><span data-stu-id="ee101-120">…</span></span> <span data-ttu-id="ee101-121">（属性 2 至属性 P-1）</span><span class="sxs-lookup"><span data-stu-id="ee101-121">(property 2 through property P-1)</span></span>
  
<span data-ttu-id="ee101-122">属性 p 的属性标记（4 个字节）</span><span class="sxs-lookup"><span data-stu-id="ee101-122">Property p's property tag (4 bytes)</span></span>
  
<span data-ttu-id="ee101-123">属性 p 的保留数据（4 个字节）</span><span class="sxs-lookup"><span data-stu-id="ee101-123">Property p's reserved data (4 bytes)</span></span>
  
<span data-ttu-id="ee101-124">属性 p 的值联合（8 个字节）</span><span class="sxs-lookup"><span data-stu-id="ee101-124">Property p's value union (8 bytes)</span></span>
  
<span data-ttu-id="ee101-125">属性 p 的值数据（0 个或可变字节）</span><span class="sxs-lookup"><span data-stu-id="ee101-125">Property p's value data (0 or variable bytes)</span></span>
  
<span data-ttu-id="ee101-126">行 2 中属性 q 的数量（4 个字节）</span><span class="sxs-lookup"><span data-stu-id="ee101-126">Number of properties q in row two (4 bytes)</span></span>
  
<span data-ttu-id="ee101-127">…</span><span class="sxs-lookup"><span data-stu-id="ee101-127">…</span></span> <span data-ttu-id="ee101-128">（行 2 的属性）</span><span class="sxs-lookup"><span data-stu-id="ee101-128">(row two's properties)</span></span>
  
<span data-ttu-id="ee101-129">…</span><span class="sxs-lookup"><span data-stu-id="ee101-129">…</span></span> <span data-ttu-id="ee101-130">（行 3 至行 n-1）</span><span class="sxs-lookup"><span data-stu-id="ee101-130">(row 3 through row n-1)</span></span>
  
<span data-ttu-id="ee101-131">行 n 中属性 r 的数量（4 个字节）</span><span class="sxs-lookup"><span data-stu-id="ee101-131">Number of properties r in row n (4 bytes)</span></span>
  
<span data-ttu-id="ee101-132">…</span><span class="sxs-lookup"><span data-stu-id="ee101-132">…</span></span> <span data-ttu-id="ee101-133">（行 n 的属性）</span><span class="sxs-lookup"><span data-stu-id="ee101-133">(row n's properties)</span></span>
  
<span data-ttu-id="ee101-134">额外信息字节计数 EI（4 个字节）</span><span class="sxs-lookup"><span data-stu-id="ee101-134">Extra information byte count EI (4 bytes)</span></span>
  
<span data-ttu-id="ee101-135">额外信息（EI 个字节）</span><span class="sxs-lookup"><span data-stu-id="ee101-135">Extra information (EI bytes)</span></span>
  
<span data-ttu-id="ee101-136">元数据（8 个字节）</span><span class="sxs-lookup"><span data-stu-id="ee101-136">Metadata (8 bytes)</span></span>
  
<span data-ttu-id="ee101-137">有关二进制结构的示例，请参阅 [Outlook 2003/2007 NK2 文件格式和开发人员指南](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)。</span><span class="sxs-lookup"><span data-stu-id="ee101-137">For an example of a binary structure, see Binary Example in the [Outlook 2003/2007 NK2 File Format and Developer Guidelines.](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)</span></span>
  
## <a name="high-level-layout"></a><span data-ttu-id="ee101-138">高级别布局</span><span class="sxs-lookup"><span data-stu-id="ee101-138">High-level Layout</span></span>

<span data-ttu-id="ee101-139">从广义上讲，自动完成流的布局如下所示：</span><span class="sxs-lookup"><span data-stu-id="ee101-139">Broadly speaking, the layout of the autocomplete stream is as follows:</span></span>
  
|<span data-ttu-id="ee101-140">**数值数据**</span><span class="sxs-lookup"><span data-stu-id="ee101-140">**Value Data**</span></span>|<span data-ttu-id="ee101-141">**字节数**</span><span class="sxs-lookup"><span data-stu-id="ee101-141">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ee101-142">元数据</span><span class="sxs-lookup"><span data-stu-id="ee101-142">Metadata</span></span>  <br/> |<span data-ttu-id="ee101-143">4</span><span class="sxs-lookup"><span data-stu-id="ee101-143">4</span></span>  <br/> |
|<span data-ttu-id="ee101-144">主要版本号</span><span class="sxs-lookup"><span data-stu-id="ee101-144">Major Version Number</span></span>  <br/> |<span data-ttu-id="ee101-145">4</span><span class="sxs-lookup"><span data-stu-id="ee101-145">4</span></span>  <br/> |
|<span data-ttu-id="ee101-146">次要版本号</span><span class="sxs-lookup"><span data-stu-id="ee101-146">Minor Version Number</span></span>  <br/> |<span data-ttu-id="ee101-147">4</span><span class="sxs-lookup"><span data-stu-id="ee101-147">4</span></span>  <br/> |
|<span data-ttu-id="ee101-148">行集</span><span class="sxs-lookup"><span data-stu-id="ee101-148">Row-set</span></span>  <br/> |<span data-ttu-id="ee101-149">变量</span><span class="sxs-lookup"><span data-stu-id="ee101-149">Variable</span></span>  <br/> |
|<span data-ttu-id="ee101-150">额外信息字节计数 EI</span><span class="sxs-lookup"><span data-stu-id="ee101-150">Extra information byte count EI</span></span>  <br/> |<span data-ttu-id="ee101-151">4</span><span class="sxs-lookup"><span data-stu-id="ee101-151">4</span></span>  <br/> |
|<span data-ttu-id="ee101-152">额外信息</span><span class="sxs-lookup"><span data-stu-id="ee101-152">Extra information</span></span>  <br/> |<span data-ttu-id="ee101-153">EI</span><span class="sxs-lookup"><span data-stu-id="ee101-153">EI</span></span>  <br/> |
|<span data-ttu-id="ee101-154">元数据</span><span class="sxs-lookup"><span data-stu-id="ee101-154">Metadata</span></span>  <br/> |<span data-ttu-id="ee101-155">8</span><span class="sxs-lookup"><span data-stu-id="ee101-155">8</span></span>  <br/> |
   
<span data-ttu-id="ee101-156">读取此数据流时，如果主要版本不同于 12，则不应读取或写入此数据流。</span><span class="sxs-lookup"><span data-stu-id="ee101-156">When reading this stream, if the major version is different than 12, then this stream should not be read or written.</span></span> <span data-ttu-id="ee101-157">自动完成流的当前次要版本为 0，其额外信息字节计数设置为 0。</span><span class="sxs-lookup"><span data-stu-id="ee101-157">The current minor version of the autocomplete stream is 0, which has the Extra Information Byte count set to 0.</span></span> <span data-ttu-id="ee101-158">如果次要版本不同于 0，则在读取数据流时需要读取的额外信息中将存在信息，并在写入数据流时保留。</span><span class="sxs-lookup"><span data-stu-id="ee101-158">If the minor version is different than 0, then there will be information in the extra information that needs to be read when reading the stream and preserved when writing the stream.</span></span> <span data-ttu-id="ee101-159">写入数据流时还需要保留次要版本。</span><span class="sxs-lookup"><span data-stu-id="ee101-159">The minor version will also need to be preserved when writing the stream.</span></span> <span data-ttu-id="ee101-160">如果未保留这两者，则写入额外信息的 Outlook 实例将会丢失数据。</span><span class="sxs-lookup"><span data-stu-id="ee101-160">If both of these are not preserved, instances of Outlook that wrote the extra information will lose data.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ee101-161">应用程序不得将自定义数据添加到“额外信息”字段或更改次要版本，因为此功能是为了支持对格式的 Outlook 扩展而不是任意第三方扩展。</span><span class="sxs-lookup"><span data-stu-id="ee101-161">Applications must not add custom data to the Extra Information field or change the minor version as this functionality is to support Outlook extensions to the format and not arbitrary third-party extensions.</span></span> 
  
## <a name="row-set-layout"></a><span data-ttu-id="ee101-162">行集布局</span><span class="sxs-lookup"><span data-stu-id="ee101-162">Row-set Layout</span></span>

<span data-ttu-id="ee101-163">行集布局如下所示：</span><span class="sxs-lookup"><span data-stu-id="ee101-163">The row-set layout is as follows:</span></span> 
  
|<span data-ttu-id="ee101-164">**数值数据**</span><span class="sxs-lookup"><span data-stu-id="ee101-164">**Value Data**</span></span>|<span data-ttu-id="ee101-165">**字节数**</span><span class="sxs-lookup"><span data-stu-id="ee101-165">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ee101-166">行数</span><span class="sxs-lookup"><span data-stu-id="ee101-166">Number of rows</span></span>  <br/> |<span data-ttu-id="ee101-167">4</span><span class="sxs-lookup"><span data-stu-id="ee101-167">4</span></span>  <br/> |
|<span data-ttu-id="ee101-168">行</span><span class="sxs-lookup"><span data-stu-id="ee101-168">Rows</span></span>  <br/> |<span data-ttu-id="ee101-169">变量</span><span class="sxs-lookup"><span data-stu-id="ee101-169">Variable</span></span>  <br/> |
   
<span data-ttu-id="ee101-170">行数将标识二进制流序列的下一部分中有多少行。</span><span class="sxs-lookup"><span data-stu-id="ee101-170">The number of rows identifies how many rows come in the next part of the binary stream sequence.</span></span>
  
## <a name="row-layout"></a><span data-ttu-id="ee101-171">行布局</span><span class="sxs-lookup"><span data-stu-id="ee101-171">Row Layout</span></span>

<span data-ttu-id="ee101-172">每行的格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="ee101-172">Each row is of the following format:</span></span>
  
|<span data-ttu-id="ee101-173">**数值数据**</span><span class="sxs-lookup"><span data-stu-id="ee101-173">**Value Data**</span></span>|<span data-ttu-id="ee101-174">**字节数**</span><span class="sxs-lookup"><span data-stu-id="ee101-174">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ee101-175">属性数量</span><span class="sxs-lookup"><span data-stu-id="ee101-175">Number of properties</span></span>  <br/> |<span data-ttu-id="ee101-176">4</span><span class="sxs-lookup"><span data-stu-id="ee101-176">4</span></span>  <br/> |
|<span data-ttu-id="ee101-177">属性</span><span class="sxs-lookup"><span data-stu-id="ee101-177">Properties</span></span>  <br/> |<span data-ttu-id="ee101-178">变量</span><span class="sxs-lookup"><span data-stu-id="ee101-178">Variable</span></span>  <br/> |
   
<span data-ttu-id="ee101-179">属性数量将标识二进制流序列的下一部分中有多少属性。</span><span class="sxs-lookup"><span data-stu-id="ee101-179">The number of properties identifies how many properties come in the next part of the binary stream sequence.</span></span>
  
## <a name="property-layout"></a><span data-ttu-id="ee101-180">属性布局</span><span class="sxs-lookup"><span data-stu-id="ee101-180">Property Layout</span></span>

<span data-ttu-id="ee101-181">每个属性的格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="ee101-181">Each property is of the following format:</span></span>
  
|<span data-ttu-id="ee101-182">**数值数据**</span><span class="sxs-lookup"><span data-stu-id="ee101-182">**Value Data**</span></span>|<span data-ttu-id="ee101-183">**字节数**</span><span class="sxs-lookup"><span data-stu-id="ee101-183">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ee101-184">属性标记</span><span class="sxs-lookup"><span data-stu-id="ee101-184">Property Tag</span></span>  <br/> |<span data-ttu-id="ee101-185">4</span><span class="sxs-lookup"><span data-stu-id="ee101-185">4</span></span>  <br/> |
|<span data-ttu-id="ee101-186">保留数据</span><span class="sxs-lookup"><span data-stu-id="ee101-186">Reserved Data</span></span>  <br/> |<span data-ttu-id="ee101-187">4</span><span class="sxs-lookup"><span data-stu-id="ee101-187">4</span></span>  <br/> |
|<span data-ttu-id="ee101-188">属性值联合</span><span class="sxs-lookup"><span data-stu-id="ee101-188">Property Value Union</span></span>  <br/> ||
|<span data-ttu-id="ee101-189">数值数据</span><span class="sxs-lookup"><span data-stu-id="ee101-189">Value Data</span></span>  <br/> |<span data-ttu-id="ee101-190">0 或变量（具体取决于属性标记）</span><span class="sxs-lookup"><span data-stu-id="ee101-190">0 or variable (depending on the prop tag)</span></span>  <br/> |
   
## <a name="interpreting-the-property-value"></a><span data-ttu-id="ee101-191">解释属性值</span><span class="sxs-lookup"><span data-stu-id="ee101-191">Interpreting the Property Value</span></span>

<span data-ttu-id="ee101-192">属性值联合和数值数据将基于属性块的前 4 个字节中的属性标记进行解释。</span><span class="sxs-lookup"><span data-stu-id="ee101-192">The Property Value Union and the Value Data are to be interpreted based on the property tag in the first 4 bytes of the property block.</span></span> <span data-ttu-id="ee101-193">此属性标记的格式与 MAPI 属性标记的格式相同。</span><span class="sxs-lookup"><span data-stu-id="ee101-193">This property tag is in the same format as a MAPI property tag.</span></span> <span data-ttu-id="ee101-194">属性标记的 0 至 15 位是属性的类型。</span><span class="sxs-lookup"><span data-stu-id="ee101-194">Bits 0 through 15 of the property tag are the property's type.</span></span> <span data-ttu-id="ee101-195">16 至 31 位是属性的标识符。</span><span class="sxs-lookup"><span data-stu-id="ee101-195">Bits 16 through 31 are the property's identifier.</span></span> <span data-ttu-id="ee101-196">属性类型确定应如何读取属性的其余部分。</span><span class="sxs-lookup"><span data-stu-id="ee101-196">The property type determines how the rest of the property should be read.</span></span>
  
## <a name="static-value"></a><span data-ttu-id="ee101-197">静态值</span><span class="sxs-lookup"><span data-stu-id="ee101-197">Static Value</span></span>

<span data-ttu-id="ee101-198">某些属性没有数值数据，仅在联合中有数据。</span><span class="sxs-lookup"><span data-stu-id="ee101-198">Some properties have no Value Data and only have data in the union.</span></span> <span data-ttu-id="ee101-199">以下属性类型（来自属性标记）可解释 8 个字节的属性联合数据，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ee101-199">The following property types (which come from the Property Tag) should interpret the 8-byte Property Union data as follows:</span></span>
  
|<span data-ttu-id="ee101-200">**属性类型**</span><span class="sxs-lookup"><span data-stu-id="ee101-200">**Prop Type**</span></span>|<span data-ttu-id="ee101-201">**属性联合解释**</span><span class="sxs-lookup"><span data-stu-id="ee101-201">**Property Union Interpretation**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ee101-202">PT_I2</span><span class="sxs-lookup"><span data-stu-id="ee101-202">PT_I2</span></span>  <br/> |<span data-ttu-id="ee101-203">short int</span><span class="sxs-lookup"><span data-stu-id="ee101-203">short int</span></span>  <br/> |
|<span data-ttu-id="ee101-204">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="ee101-204">PT_LONG</span></span>  <br/> |<span data-ttu-id="ee101-205">long</span><span class="sxs-lookup"><span data-stu-id="ee101-205">long</span></span>  <br/> |
|<span data-ttu-id="ee101-206">PT_R4</span><span class="sxs-lookup"><span data-stu-id="ee101-206">PT_R4</span></span>  <br/> |<span data-ttu-id="ee101-207">float</span><span class="sxs-lookup"><span data-stu-id="ee101-207">float</span></span>  <br/> |
|<span data-ttu-id="ee101-208">PT_DOUBLE</span><span class="sxs-lookup"><span data-stu-id="ee101-208">PT_DOUBLE</span></span>  <br/> |<span data-ttu-id="ee101-209">double</span><span class="sxs-lookup"><span data-stu-id="ee101-209">double</span></span>  <br/> |
|<span data-ttu-id="ee101-210">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="ee101-210">PT_BOOLEAN</span></span>  <br/> |<span data-ttu-id="ee101-211">short int</span><span class="sxs-lookup"><span data-stu-id="ee101-211">short int</span></span>  <br/> |
|<span data-ttu-id="ee101-212">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="ee101-212">PT_SYSTIME</span></span>  <br/> |<span data-ttu-id="ee101-213">FILETIME</span><span class="sxs-lookup"><span data-stu-id="ee101-213">FILETIME</span></span>  <br/> |
|<span data-ttu-id="ee101-214">PT_I8</span><span class="sxs-lookup"><span data-stu-id="ee101-214">PT_I8</span></span>  <br/> |<span data-ttu-id="ee101-215">LARGE_INTEGER</span><span class="sxs-lookup"><span data-stu-id="ee101-215">LARGE_INTEGER</span></span>  <br/> |
   
## <a name="dynamic-values"></a><span data-ttu-id="ee101-216">动态值</span><span class="sxs-lookup"><span data-stu-id="ee101-216">Dynamic Values</span></span>

<span data-ttu-id="ee101-217">其他属性具有在包含属性标记、保留数据和属性值联合的前 16 个字节之后的数值数据块中的数据。</span><span class="sxs-lookup"><span data-stu-id="ee101-217">Other properties have data in a Value Data block after the first 16 bytes that contain the Property Tag, the Reserved Data, and the Property Value Union.</span></span> <span data-ttu-id="ee101-218">与静态值不同，存储在 8 个字节属性值联合中的数据与读取无关。</span><span class="sxs-lookup"><span data-stu-id="ee101-218">Unlike static values, the data that is stored in the 8-byte Property Value union is irrelevant on reading.</span></span> <span data-ttu-id="ee101-219">写入时，请确保使用某些内容填充这 8 个字节。</span><span class="sxs-lookup"><span data-stu-id="ee101-219">When writing, make sure that you fill these 8 bytes with something.</span></span> <span data-ttu-id="ee101-220">但是，这 8 个字节的内容并不重要。</span><span class="sxs-lookup"><span data-stu-id="ee101-220">However, the content of the 8 bytes is not important.</span></span> <span data-ttu-id="ee101-221">在动态值中，属性标记的类型确定如何解释数值数据。</span><span class="sxs-lookup"><span data-stu-id="ee101-221">In dynamic values, the property tag's type determines how to interpret the Value Data.</span></span>
  
<span data-ttu-id="ee101-222">PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="ee101-222">PT_STRING8</span></span> 
  
|<span data-ttu-id="ee101-223">**数值数据**</span><span class="sxs-lookup"><span data-stu-id="ee101-223">**Value Data**</span></span>|<span data-ttu-id="ee101-224">**字节数**</span><span class="sxs-lookup"><span data-stu-id="ee101-224">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ee101-225">字节数量 n</span><span class="sxs-lookup"><span data-stu-id="ee101-225">Number of bytes n</span></span>  <br/> |<span data-ttu-id="ee101-226">4</span><span class="sxs-lookup"><span data-stu-id="ee101-226">4</span></span>  <br/> |
|<span data-ttu-id="ee101-227">解释为 ANSI 字符串（包括 NULL 终止符）的字节</span><span class="sxs-lookup"><span data-stu-id="ee101-227">Bytes to be interpreted as an ANSI string (includes NULL terminator)</span></span>  <br/> |<span data-ttu-id="ee101-228">n</span><span class="sxs-lookup"><span data-stu-id="ee101-228">n</span></span>  <br/> |
   
<span data-ttu-id="ee101-229">PT_CLSID</span><span class="sxs-lookup"><span data-stu-id="ee101-229">PT_CLSID</span></span>
  
|<span data-ttu-id="ee101-230">**数值数据**</span><span class="sxs-lookup"><span data-stu-id="ee101-230">**Value Data**</span></span>|<span data-ttu-id="ee101-231">**字节数**</span><span class="sxs-lookup"><span data-stu-id="ee101-231">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ee101-232">解释为 GUID 的字节</span><span class="sxs-lookup"><span data-stu-id="ee101-232">Bytes to be interpreted as a GUID</span></span>  <br/> |<span data-ttu-id="ee101-233">16</span><span class="sxs-lookup"><span data-stu-id="ee101-233">16</span></span>  <br/> |
|||
   
<span data-ttu-id="ee101-234">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="ee101-234">PT_BINARY</span></span> 
  
|<span data-ttu-id="ee101-235">**数值数据**</span><span class="sxs-lookup"><span data-stu-id="ee101-235">**Value Data**</span></span>|<span data-ttu-id="ee101-236">**字节数**</span><span class="sxs-lookup"><span data-stu-id="ee101-236">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ee101-237">字节数量 n</span><span class="sxs-lookup"><span data-stu-id="ee101-237">Number of bytes n</span></span>  <br/> |<span data-ttu-id="ee101-238">4</span><span class="sxs-lookup"><span data-stu-id="ee101-238">4</span></span>  <br/> |
|<span data-ttu-id="ee101-239">解释为字节数组的字节</span><span class="sxs-lookup"><span data-stu-id="ee101-239">Bytes to be interpreted as a byte array</span></span>  <br/> |<span data-ttu-id="ee101-240">n</span><span class="sxs-lookup"><span data-stu-id="ee101-240">n</span></span>  <br/> |
   
<span data-ttu-id="ee101-241">PT_ERROR</span><span class="sxs-lookup"><span data-stu-id="ee101-241">PT_ERROR</span></span>
  
|<span data-ttu-id="ee101-242">**数值数据**</span><span class="sxs-lookup"><span data-stu-id="ee101-242">**Value Data**</span></span>|<span data-ttu-id="ee101-243">**字节数**</span><span class="sxs-lookup"><span data-stu-id="ee101-243">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ee101-244">字节数量 n</span><span class="sxs-lookup"><span data-stu-id="ee101-244">Number of bytes n</span></span>  <br/> |<span data-ttu-id="ee101-245">4</span><span class="sxs-lookup"><span data-stu-id="ee101-245">4</span></span>  <br/> |
|<span data-ttu-id="ee101-246">解释为字节数组的字节</span><span class="sxs-lookup"><span data-stu-id="ee101-246">Bytes to be interpreted as a byte array</span></span>  <br/> |<span data-ttu-id="ee101-247">n</span><span class="sxs-lookup"><span data-stu-id="ee101-247">n</span></span>  <br/> |
   
<span data-ttu-id="ee101-248">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="ee101-248">PT_MV_BINARY</span></span>
  
|<span data-ttu-id="ee101-249">**数值数据**</span><span class="sxs-lookup"><span data-stu-id="ee101-249">**Value Data**</span></span>|<span data-ttu-id="ee101-250">**字节数**</span><span class="sxs-lookup"><span data-stu-id="ee101-250">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ee101-251">二进制数组数量 X</span><span class="sxs-lookup"><span data-stu-id="ee101-251">Number of binary arrays X</span></span>  <br/> |<span data-ttu-id="ee101-252">4</span><span class="sxs-lookup"><span data-stu-id="ee101-252">4</span></span>  <br/> |
|<span data-ttu-id="ee101-253">包含 X 个二进制数组的一串字节。</span><span class="sxs-lookup"><span data-stu-id="ee101-253">A run of bytes that contains X binary arrays.</span></span> <span data-ttu-id="ee101-254">每个数组应完全解释为 PT_BINARY 字节串。</span><span class="sxs-lookup"><span data-stu-id="ee101-254">Each array should be interpreted exactly like the PT_BINARY byte run.</span></span>  <br/> |<span data-ttu-id="ee101-255">变量</span><span class="sxs-lookup"><span data-stu-id="ee101-255">Variable</span></span>  <br/> |
   
<span data-ttu-id="ee101-256">PT_MV_STRING8 (Outlook 2007, Outlook 2010, and Outlook 2013)</span><span class="sxs-lookup"><span data-stu-id="ee101-256">PT_MV_STRING8 (Outlook 2007, Outlook 2010, and Outlook 2013)</span></span>
  
|<span data-ttu-id="ee101-257">**数值数据**</span><span class="sxs-lookup"><span data-stu-id="ee101-257">**Value Data**</span></span>|<span data-ttu-id="ee101-258">**字节数**</span><span class="sxs-lookup"><span data-stu-id="ee101-258">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ee101-259">ANSI 字符串数量 X</span><span class="sxs-lookup"><span data-stu-id="ee101-259">Number of ANSI strings X</span></span>  <br/> |<span data-ttu-id="ee101-260">4</span><span class="sxs-lookup"><span data-stu-id="ee101-260">4</span></span>  <br/> |
|<span data-ttu-id="ee101-261">包含 X 个 ANSI 字符串的一串字节。</span><span class="sxs-lookup"><span data-stu-id="ee101-261">A run of bytes that contains X ANSI strings.</span></span> <span data-ttu-id="ee101-262">每个字符串应完全解释为 PT_STRING8 字节串。</span><span class="sxs-lookup"><span data-stu-id="ee101-262">Each string should be interpreted exactly like the PT_STRING8 byte run.</span></span>  <br/> |<span data-ttu-id="ee101-263">变量</span><span class="sxs-lookup"><span data-stu-id="ee101-263">Variable</span></span>  <br/> |
   
<span data-ttu-id="ee101-264">PT_MV_UNICODE (Outlook 2007, Outlook 2010, Outlook 2013)</span><span class="sxs-lookup"><span data-stu-id="ee101-264">PT_MV_UNICODE (Outlook 2007, Outlook 2010, Outlook 2013)</span></span>
  
|<span data-ttu-id="ee101-265">**数值数据**</span><span class="sxs-lookup"><span data-stu-id="ee101-265">**Value Data**</span></span>|<span data-ttu-id="ee101-266">**字节数**</span><span class="sxs-lookup"><span data-stu-id="ee101-266">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ee101-267">UNICODE 字符串数量 X</span><span class="sxs-lookup"><span data-stu-id="ee101-267">Number of UNICODE strings X</span></span>  <br/> |<span data-ttu-id="ee101-268">4</span><span class="sxs-lookup"><span data-stu-id="ee101-268">4</span></span>  <br/> |
|<span data-ttu-id="ee101-269">包含 X 个 UNICODE 字符串的一串字节。</span><span class="sxs-lookup"><span data-stu-id="ee101-269">A run of bytes that contains X UNICODE strings.</span></span> <span data-ttu-id="ee101-270">每个数组应完全解释为 PT_UNICODE 字节串。</span><span class="sxs-lookup"><span data-stu-id="ee101-270">Each string should be interpreted exactly like the PT_UNICODE byte run.</span></span>  <br/> |<span data-ttu-id="ee101-271">变量</span><span class="sxs-lookup"><span data-stu-id="ee101-271">Variable</span></span>  <br/> |
   
## <a name="significant-properties"></a><span data-ttu-id="ee101-272">重要属性</span><span class="sxs-lookup"><span data-stu-id="ee101-272">Significant properties</span></span>

<span data-ttu-id="ee101-273">如本主题前面所述，表示属性的二进制块具有与通讯簿收件人的属性对应的属性标记。</span><span class="sxs-lookup"><span data-stu-id="ee101-273">As mentioned previously in this topic, the binary blocks that represent properties have property tags that correspond to properties on address book recipients.</span></span> <span data-ttu-id="ee101-274">对于此处未列出的属性，可以在 https://msdn.microsoft.com/library/cc433490(EXCHG.80).aspx 查找属性说明。</span><span class="sxs-lookup"><span data-stu-id="ee101-274">For properties that are not listed here, you can look up the property description at https://msdn.microsoft.com/library/cc433490(EXCHG.80).aspx.</span></span>
  
|<span data-ttu-id="ee101-275">**属性名称**</span><span class="sxs-lookup"><span data-stu-id="ee101-275">**Property Name**</span></span>|<span data-ttu-id="ee101-276">**属性标记**</span><span class="sxs-lookup"><span data-stu-id="ee101-276">**Property Tag**</span></span>|<span data-ttu-id="ee101-277">**说明（请参阅 MSDN 获取详细信息）**</span><span class="sxs-lookup"><span data-stu-id="ee101-277">**Description (see MSDN for more information)**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ee101-278">PR_NICK_NAME_W（不在收件人上传输，仅特定于自动完成流）</span><span class="sxs-lookup"><span data-stu-id="ee101-278">PR_NICK_NAME_W (not transmitted on recipients, specific to autocomplete stream only)</span></span>  <br/> |<span data-ttu-id="ee101-279">0x6001001f</span><span class="sxs-lookup"><span data-stu-id="ee101-279">0x6001001f</span></span>  <br/> |<span data-ttu-id="ee101-280">此属性必须位于每个收件人行中的首位。</span><span class="sxs-lookup"><span data-stu-id="ee101-280">This property must be first in each recipient row.</span></span> <span data-ttu-id="ee101-281">它在功能上作为收件人行的密钥标识符。</span><span class="sxs-lookup"><span data-stu-id="ee101-281">It functionally serves as a key identifier for the recipient row.</span></span>  <br/> |
|<span data-ttu-id="ee101-282">PR_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="ee101-282">PR_ENTRYID</span></span>  <br/> |<span data-ttu-id="ee101-283">0x0FFF0102</span><span class="sxs-lookup"><span data-stu-id="ee101-283">0x0FFF0102</span></span>  <br/> |<span data-ttu-id="ee101-284">收件人的通讯簿条目标识符。</span><span class="sxs-lookup"><span data-stu-id="ee101-284">The address book entry identifier for the recipient.</span></span>  <br/> |
|<span data-ttu-id="ee101-285">PR_DISPLAY_NAME_W</span><span class="sxs-lookup"><span data-stu-id="ee101-285">PR_DISPLAY_NAME_W</span></span>  <br/> |<span data-ttu-id="ee101-286">0x3001001F</span><span class="sxs-lookup"><span data-stu-id="ee101-286">0x3001001F</span></span>  <br/> |<span data-ttu-id="ee101-287">收件人的显示名称。</span><span class="sxs-lookup"><span data-stu-id="ee101-287">The recipient's display name.</span></span>  <br/> |
|<span data-ttu-id="ee101-288">PR_EMAIL_ADDRESS_W</span><span class="sxs-lookup"><span data-stu-id="ee101-288">PR_EMAIL_ADDRESS_W</span></span>  <br/> |<span data-ttu-id="ee101-289">0x3003001F</span><span class="sxs-lookup"><span data-stu-id="ee101-289">0x3003001F</span></span>  <br/> |<span data-ttu-id="ee101-290">收件人的电子邮件地址（例如 johndoe@contoso.com 或 /o=Contoso/OU=Foo/cn=Recipients/cn=johndoe）</span><span class="sxs-lookup"><span data-stu-id="ee101-290">The recipient's email address (e.g. johndoe@contoso.com or /o=Contoso/OU=Foo/cn=Recipients/cn=johndoe)</span></span>  <br/> |
|<span data-ttu-id="ee101-291">PR_ADDRTYPE_W</span><span class="sxs-lookup"><span data-stu-id="ee101-291">PR_ADDRTYPE_W</span></span>  <br/> |<span data-ttu-id="ee101-292">0x3002001F</span><span class="sxs-lookup"><span data-stu-id="ee101-292">0x3002001F</span></span>  <br/> |<span data-ttu-id="ee101-293">收件人的地址类型（例如 SMTP 或 EX）。</span><span class="sxs-lookup"><span data-stu-id="ee101-293">The recipient's address type (e.g. SMTP or EX).</span></span>  <br/> |
|<span data-ttu-id="ee101-294">PR_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="ee101-294">PR_SEARCH_KEY</span></span>  <br/> |<span data-ttu-id="ee101-295">0x300B0102</span><span class="sxs-lookup"><span data-stu-id="ee101-295">0x300B0102</span></span>  <br/> |<span data-ttu-id="ee101-296">收件人的 MAPI 搜索关键字。</span><span class="sxs-lookup"><span data-stu-id="ee101-296">The recipient's MAPI search key.</span></span>  <br/> |
|<span data-ttu-id="ee101-297">PR_SMTP_ADDRESS_W</span><span class="sxs-lookup"><span data-stu-id="ee101-297">PR_SMTP_ADDRESS_W</span></span>  <br/> |<span data-ttu-id="ee101-298">0x39FE001f</span><span class="sxs-lookup"><span data-stu-id="ee101-298">0x39FE001f</span></span>  <br/> |<span data-ttu-id="ee101-299">收件人的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="ee101-299">The recipient's SMTP address.</span></span>  <br/> |
|<span data-ttu-id="ee101-300">PR_DROPDOWN_DISPLAY_NAME_W（不在收件人上传输，仅特定于自动完成流）</span><span class="sxs-lookup"><span data-stu-id="ee101-300">PR_DROPDOWN_DISPLAY_NAME_W (not transmitted on recipients, specific to autocomplete stream only)</span></span>  <br/> |<span data-ttu-id="ee101-301">0X6003001f</span><span class="sxs-lookup"><span data-stu-id="ee101-301">0X6003001f</span></span>  <br/> |<span data-ttu-id="ee101-302">显示在自动完成列表中的显示字符串。</span><span class="sxs-lookup"><span data-stu-id="ee101-302">The display string that appears in the autocomplete list.</span></span>  <br/> |
|<span data-ttu-id="ee101-303">PR_NICK_NAME_WEIGHT（不在收件人上传输，仅特定于自动完成流）</span><span class="sxs-lookup"><span data-stu-id="ee101-303">PR_NICK_NAME_WEIGHT (not transmitted on recipients, specific to autocomplete stream only)</span></span>  <br/> |<span data-ttu-id="ee101-304">0x60040003</span><span class="sxs-lookup"><span data-stu-id="ee101-304">0x60040003</span></span>  <br/> |<span data-ttu-id="ee101-305">此自动完成条目的权重。</span><span class="sxs-lookup"><span data-stu-id="ee101-305">The weight of this autocomplete entry.</span></span> <span data-ttu-id="ee101-306">权重用于确定匹配自动完成列表时自动完成条目发生的顺序。</span><span class="sxs-lookup"><span data-stu-id="ee101-306">The weight is used to determine in what order autocomplete entries occur when matching the autocomplete list.</span></span> <span data-ttu-id="ee101-307">具有较高权重的条目将显示在具有较低权重的条目前面。</span><span class="sxs-lookup"><span data-stu-id="ee101-307">Entries with higher weight will show before entries with lower weight.</span></span> <span data-ttu-id="ee101-308">完整的自动完成列表按此属性排序。</span><span class="sxs-lookup"><span data-stu-id="ee101-308">The complete autocomplete list is sorted by this property.</span></span> <span data-ttu-id="ee101-309">权重会随着时间的推移逐渐减少，并在用户向此收件人发送电子邮件时增加。</span><span class="sxs-lookup"><span data-stu-id="ee101-309">The weight periodically decreases over time and increases when the user sends an email to this recipient.</span></span> <span data-ttu-id="ee101-310">有关此属性的详细信息，请参阅本主题后面的说明。</span><span class="sxs-lookup"><span data-stu-id="ee101-310">See the description later in this topic for more information about this property.</span></span>  <br/> |
   
<span data-ttu-id="ee101-311">PR_NICK_NAME_WEIGHT</span><span class="sxs-lookup"><span data-stu-id="ee101-311">PR_NICK_NAME_WEIGHT</span></span>
  
<span data-ttu-id="ee101-312">自动完成流中的行集按 PR_NICK_NAME_WEIGHT 属性以降序顺序进行排序，并且自动完成流应始终保留此排序特征。</span><span class="sxs-lookup"><span data-stu-id="ee101-312">The set of rows in the autocomplete stream is sorted in descending order by the PR_NICK_NAME_WEIGHT property and the autocomplete stream should always preserve this sorted characteristic.</span></span> <span data-ttu-id="ee101-313">因此，对行的权重的任何更改也应确保行的位置维护整个行集的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="ee101-313">Therefore, any changes to a row's weight should also ensure that the row's position maintains the sorted order of the complete set of rows.</span></span> <span data-ttu-id="ee101-314">应将行集的任何添加项插入到正确的位置以维护该排序顺序。</span><span class="sxs-lookup"><span data-stu-id="ee101-314">Any additions to the row-set should be inserted to the correct position to maintain the sorted order.</span></span>
  
<span data-ttu-id="ee101-315">此权重的最小值为 0x1，最大值为 LONG_MAX。</span><span class="sxs-lookup"><span data-stu-id="ee101-315">The minimum value of this weight is 0x1 and the maximum value is LONG_MAX.</span></span> <span data-ttu-id="ee101-316">权重的任何其他值都被视为无效。</span><span class="sxs-lookup"><span data-stu-id="ee101-316">Any other values for the weight are considered invalid.</span></span>
  
<span data-ttu-id="ee101-317">当 Outlook 2007 向收件人发送邮件或解析收件人时，它会将该收件人的权重增加 0x2000。</span><span class="sxs-lookup"><span data-stu-id="ee101-317">When Outlook 2007 sends a mail to or resolves a recipient, it will increase that recipient's weight by 0x2000.</span></span>
  

