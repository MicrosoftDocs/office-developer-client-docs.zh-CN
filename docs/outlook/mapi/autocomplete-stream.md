---
title: 记忆式键入流
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: d4f380fa-2ed9-4c7c-9ef3-b32f8409f657
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 7fc1fae4ed648d59c273b20ced247f6d20e01a6f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774600"
---
# <a name="autocomplete-stream"></a><span data-ttu-id="1b0ed-103">记忆式键入流</span><span class="sxs-lookup"><span data-stu-id="1b0ed-103">Autocomplete Stream</span></span>

  
  
<span data-ttu-id="1b0ed-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1b0ed-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1b0ed-105">除了了解 Microsoft Outlook 与记忆式键入数据流的交互方式，您还必须了解记忆式键入 stream 的二进制格式。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-105">In addition to knowing how Microsoft Outlook interacts with the autocomplete stream, you must also understand the binary format of the autocomplete stream.</span></span>
  
<span data-ttu-id="1b0ed-106">记忆式键入流是一组收件人属性行的保存为二进制流以及仅由 Microsoft Outlook 2013、 Microsoft Outlook 2010、 Microsoft Office Outlook 2007 中，和 Microsoft Outlook 2003 一些记帐元数据。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-106">The autocomplete stream is a set of recipient property rows that are saved as a binary stream together with some bookkeeping metadata that is used only by Microsoft Outlook 2013, Microsoft Outlook 2010, Microsoft Office Outlook 2007, and Microsoft Outlook 2003.</span></span> <span data-ttu-id="1b0ed-107">元数据是与记忆式键入流 Outlook 交互相关，因此第三方必须保留它们保存修改后的记忆式键入流时在每个元数据块新增。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-107">The metadata is relevant to Outlook interactions with the autocomplete stream so third parties must preserve what is in each metadata block when they save a modified autocomplete stream.</span></span> <span data-ttu-id="1b0ed-108">换句话说，第三方应修改仅二进制格式的行集一部分和保留内容已在记忆式键入流的元数据块。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-108">In other words, third parties should modify only the row-set part of the binary format and preserve what was already in the metadata blocks of the autocomplete stream.</span></span>
  
## <a name="stream-visualization"></a><span data-ttu-id="1b0ed-109">流可视化</span><span class="sxs-lookup"><span data-stu-id="1b0ed-109">Stream Visualization</span></span>

<span data-ttu-id="1b0ed-110">记忆式键入流的高级布局是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1b0ed-110">The high-level layout of the autocomplete stream is as follows:</span></span>
  
<span data-ttu-id="1b0ed-111">元数据 （4 个字节）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-111">Metadata (4 bytes)</span></span>
  
<span data-ttu-id="1b0ed-112">主版本号 （4 个字节）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-112">Major Version Number (4 bytes)</span></span>
  
<span data-ttu-id="1b0ed-113">次要版本号 （4 个字节）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-113">Minor Version Number (4 bytes)</span></span>
  
<span data-ttu-id="1b0ed-114">行 n （4 个字节） 的数目</span><span class="sxs-lookup"><span data-stu-id="1b0ed-114">Number of rows n (4 bytes)</span></span>
  
<span data-ttu-id="1b0ed-115">第一行 （4 个字节） 中的属性 p 的数目</span><span class="sxs-lookup"><span data-stu-id="1b0ed-115">Number of properties p in row one (4 bytes)</span></span>
  
<span data-ttu-id="1b0ed-116">属性 1 的属性标记 （4 个字节）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-116">Property 1's property tag (4 bytes)</span></span>
  
<span data-ttu-id="1b0ed-117">属性 1 的保留数据 （4 个字节）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-117">Property 1's reserved data (4 bytes)</span></span>
  
<span data-ttu-id="1b0ed-118">1 的属性值 union （8 个字节）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-118">Property 1's value union (8 bytes)</span></span>
  
<span data-ttu-id="1b0ed-119">1 的属性值数据 （0 或变量字节）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-119">Property 1's value data (0 or variable bytes)</span></span>
  
<span data-ttu-id="1b0ed-120">…</span><span class="sxs-lookup"><span data-stu-id="1b0ed-120"></span></span> <span data-ttu-id="1b0ed-121">（通过属性 P-1 属性 2）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-121">(property 2 through property P-1)</span></span>
  
<span data-ttu-id="1b0ed-122">属性 p 的属性标记 （4 个字节）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-122">Property p's property tag (4 bytes)</span></span>
  
<span data-ttu-id="1b0ed-123">属性 p 的保留数据 （4 个字节）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-123">Property p's reserved data (4 bytes)</span></span>
  
<span data-ttu-id="1b0ed-124">P 的属性值 union （8 个字节）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-124">Property p's value union (8 bytes)</span></span>
  
<span data-ttu-id="1b0ed-125">P 的属性值数据 （0 或变量字节）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-125">Property p's value data (0 or variable bytes)</span></span>
  
<span data-ttu-id="1b0ed-126">第二行中的属性 q （4 个字节） 的数目</span><span class="sxs-lookup"><span data-stu-id="1b0ed-126">Number of properties q in row two (4 bytes)</span></span>
  
<span data-ttu-id="1b0ed-127">…</span><span class="sxs-lookup"><span data-stu-id="1b0ed-127"></span></span> <span data-ttu-id="1b0ed-128">（行 2 的属性）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-128">(row two's properties)</span></span>
  
<span data-ttu-id="1b0ed-129">…</span><span class="sxs-lookup"><span data-stu-id="1b0ed-129"></span></span> <span data-ttu-id="1b0ed-130">（通过行 n-1 第 3 行）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-130">(row 3 through row n-1)</span></span>
  
<span data-ttu-id="1b0ed-131">属性 r 行 n （4 个字节） 中的数目</span><span class="sxs-lookup"><span data-stu-id="1b0ed-131">Number of properties r in row n (4 bytes)</span></span>
  
<span data-ttu-id="1b0ed-132">…</span><span class="sxs-lookup"><span data-stu-id="1b0ed-132"></span></span> <span data-ttu-id="1b0ed-133">(行 n's 属性)</span><span class="sxs-lookup"><span data-stu-id="1b0ed-133">(row n's properties)</span></span>
  
<span data-ttu-id="1b0ed-134">额外信息字节数 EI （4 个字节）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-134">Extra information byte count EI (4 bytes)</span></span>
  
<span data-ttu-id="1b0ed-135">额外信息 （EI 字节）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-135">Extra information (EI bytes)</span></span>
  
<span data-ttu-id="1b0ed-136">元数据 （8 个字节）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-136">Metadata (8 bytes)</span></span>
  
<span data-ttu-id="1b0ed-137">二进制结构的示例，请参阅中的二进制示例[Outlook 2003/2007 NK2 文件格式和开发人员的准则。](http://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)</span><span class="sxs-lookup"><span data-stu-id="1b0ed-137">For an example of a binary structure, see Binary Example in the [Outlook 2003/2007 NK2 File Format and Developer Guidelines.](http://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)</span></span>
  
## <a name="high-level-layout"></a><span data-ttu-id="1b0ed-138">高级布局</span><span class="sxs-lookup"><span data-stu-id="1b0ed-138">High-level Layout</span></span>

<span data-ttu-id="1b0ed-139">概括地说，记忆式键入 stream 的布局如下所示：</span><span class="sxs-lookup"><span data-stu-id="1b0ed-139">Broadly speaking, the layout of the autocomplete stream is as follows:</span></span>
  
|<span data-ttu-id="1b0ed-140">**值数据**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-140">**Value Data**</span></span>|<span data-ttu-id="1b0ed-141">**字节数**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-141">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b0ed-142">元数据</span><span class="sxs-lookup"><span data-stu-id="1b0ed-142">Metadata</span></span>  <br/> |<span data-ttu-id="1b0ed-143">4</span><span class="sxs-lookup"><span data-stu-id="1b0ed-143">4</span></span>  <br/> |
|<span data-ttu-id="1b0ed-144">主版本号</span><span class="sxs-lookup"><span data-stu-id="1b0ed-144">Major Version Number</span></span>  <br/> |<span data-ttu-id="1b0ed-145">4</span><span class="sxs-lookup"><span data-stu-id="1b0ed-145">4</span></span>  <br/> |
|<span data-ttu-id="1b0ed-146">次版本号</span><span class="sxs-lookup"><span data-stu-id="1b0ed-146">Minor Version Number</span></span>  <br/> |<span data-ttu-id="1b0ed-147">4</span><span class="sxs-lookup"><span data-stu-id="1b0ed-147">4</span></span>  <br/> |
|<span data-ttu-id="1b0ed-148">行集</span><span class="sxs-lookup"><span data-stu-id="1b0ed-148">Row-set</span></span>  <br/> |<span data-ttu-id="1b0ed-149">变量</span><span class="sxs-lookup"><span data-stu-id="1b0ed-149">Variable</span></span>  <br/> |
|<span data-ttu-id="1b0ed-150">额外信息字节数 EI</span><span class="sxs-lookup"><span data-stu-id="1b0ed-150">Extra information byte count EI</span></span>  <br/> |<span data-ttu-id="1b0ed-151">4</span><span class="sxs-lookup"><span data-stu-id="1b0ed-151">4</span></span>  <br/> |
|<span data-ttu-id="1b0ed-152">额外信息</span><span class="sxs-lookup"><span data-stu-id="1b0ed-152">Extra information</span></span>  <br/> |<span data-ttu-id="1b0ed-153">EI</span><span class="sxs-lookup"><span data-stu-id="1b0ed-153">EI</span></span>  <br/> |
|<span data-ttu-id="1b0ed-154">元数据</span><span class="sxs-lookup"><span data-stu-id="1b0ed-154">Metadata</span></span>  <br/> |<span data-ttu-id="1b0ed-155">8</span><span class="sxs-lookup"><span data-stu-id="1b0ed-155">8</span></span>  <br/> |
   
<span data-ttu-id="1b0ed-156">读取数据时此流，如果的主要版本不同于 12，然后此流不应读取或写入。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-156">When reading this stream, if the major version is different than 12, then this stream should not be read or written.</span></span> <span data-ttu-id="1b0ed-157">记忆式键入 stream 的当前的次要版本是 0，已设置为 0 的额外信息字节数。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-157">The current minor version of the autocomplete stream is 0, which has the Extra Information Byte count set to 0.</span></span> <span data-ttu-id="1b0ed-158">如果不同于 0 次要版本，然后将会在需要时读取流读取和写入 stream 时保留的额外信息的信息。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-158">If the minor version is different than 0, then there will be information in the extra information that needs to be read when reading the stream and preserved when writing the stream.</span></span> <span data-ttu-id="1b0ed-159">此外需要编写流时保留次要版本。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-159">The minor version will also need to be preserved when writing the stream.</span></span> <span data-ttu-id="1b0ed-160">如果这两个不保留，实例编写的额外信息的 Outlook 会丢失数据。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-160">If both of these are not preserved, instances of Outlook that wrote the extra information will lose data.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1b0ed-161">应用程序不必须将自定义数据添加到的额外信息字段或更改次要版本，如旨在支持为格式的 Outlook 扩展; 并不任意第三方扩展此功能。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-161">Applications must not add custom data to the Extra Information field or change the minor version as this functionality is to support Outlook extensions to the format and not arbitrary third-party extensions.</span></span> 
  
## <a name="row-set-layout"></a><span data-ttu-id="1b0ed-162">行集布局</span><span class="sxs-lookup"><span data-stu-id="1b0ed-162">Row-set Layout</span></span>

<span data-ttu-id="1b0ed-163">行集布局如下所示：</span><span class="sxs-lookup"><span data-stu-id="1b0ed-163">The row-set layout is as follows:</span></span> 
  
|<span data-ttu-id="1b0ed-164">**值数据**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-164">**Value Data**</span></span>|<span data-ttu-id="1b0ed-165">**字节数**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-165">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b0ed-166">行数</span><span class="sxs-lookup"><span data-stu-id="1b0ed-166">Number of rows</span></span>  <br/> |<span data-ttu-id="1b0ed-167">4</span><span class="sxs-lookup"><span data-stu-id="1b0ed-167">4</span></span>  <br/> |
|<span data-ttu-id="1b0ed-168">Rows</span><span class="sxs-lookup"><span data-stu-id="1b0ed-168">Rows</span></span>  <br/> |<span data-ttu-id="1b0ed-169">变量</span><span class="sxs-lookup"><span data-stu-id="1b0ed-169">Variable</span></span>  <br/> |
   
<span data-ttu-id="1b0ed-170">行数标识多少行并非在二进制流序列的下一部分。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-170">The number of rows identifies how many rows come in the next part of the binary stream sequence.</span></span>
  
## <a name="row-layout"></a><span data-ttu-id="1b0ed-171">行布局</span><span class="sxs-lookup"><span data-stu-id="1b0ed-171">Row Layout</span></span>

<span data-ttu-id="1b0ed-172">每一行都是以下格式：</span><span class="sxs-lookup"><span data-stu-id="1b0ed-172">Each row is of the following format:</span></span>
  
|<span data-ttu-id="1b0ed-173">**值数据**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-173">**Value Data**</span></span>|<span data-ttu-id="1b0ed-174">**字节数**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-174">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b0ed-175">属性数</span><span class="sxs-lookup"><span data-stu-id="1b0ed-175">Number of properties</span></span>  <br/> |<span data-ttu-id="1b0ed-176">4</span><span class="sxs-lookup"><span data-stu-id="1b0ed-176">4</span></span>  <br/> |
|<span data-ttu-id="1b0ed-177">属性</span><span class="sxs-lookup"><span data-stu-id="1b0ed-177">Properties</span></span>  <br/> |<span data-ttu-id="1b0ed-178">变量</span><span class="sxs-lookup"><span data-stu-id="1b0ed-178">Variable</span></span>  <br/> |
   
<span data-ttu-id="1b0ed-179">属性数标识多少属性并非在二进制流序列的下一部分。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-179">The number of properties identifies how many properties come in the next part of the binary stream sequence.</span></span>
  
## <a name="property-layout"></a><span data-ttu-id="1b0ed-180">属性布局</span><span class="sxs-lookup"><span data-stu-id="1b0ed-180">Property Layout</span></span>

<span data-ttu-id="1b0ed-181">每个属性属于以下格式：</span><span class="sxs-lookup"><span data-stu-id="1b0ed-181">Each property is of the following format:</span></span>
  
|<span data-ttu-id="1b0ed-182">**值数据**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-182">**Value Data**</span></span>|<span data-ttu-id="1b0ed-183">**字节数**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-183">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b0ed-184">属性标记</span><span class="sxs-lookup"><span data-stu-id="1b0ed-184">Property Tag</span></span>  <br/> |<span data-ttu-id="1b0ed-185">4</span><span class="sxs-lookup"><span data-stu-id="1b0ed-185">4</span></span>  <br/> |
|<span data-ttu-id="1b0ed-186">保留的数据</span><span class="sxs-lookup"><span data-stu-id="1b0ed-186">Reserved Data</span></span>  <br/> |<span data-ttu-id="1b0ed-187">4</span><span class="sxs-lookup"><span data-stu-id="1b0ed-187">4</span></span>  <br/> |
|<span data-ttu-id="1b0ed-188">属性值 Union</span><span class="sxs-lookup"><span data-stu-id="1b0ed-188">Property Value Union</span></span>  <br/> ||
|<span data-ttu-id="1b0ed-189">值数据</span><span class="sxs-lookup"><span data-stu-id="1b0ed-189">Value Data</span></span>  <br/> |<span data-ttu-id="1b0ed-190">0 或变量 （具体取决于属性标记中）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-190">0 or variable (depending on the prop tag)</span></span>  <br/> |
   
## <a name="interpreting-the-property-value"></a><span data-ttu-id="1b0ed-191">解释属性值</span><span class="sxs-lookup"><span data-stu-id="1b0ed-191">Interpreting the Property Value</span></span>

<span data-ttu-id="1b0ed-192">属性值 Union 和值数据是基于属性块的前 4 个字节中的属性标记解释。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-192">The Property Value Union and the Value Data are to be interpreted based on the property tag in the first 4 bytes of the property block.</span></span> <span data-ttu-id="1b0ed-193">此属性标记是一个 MAPI 属性标记为相同的格式。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-193">This property tag is in the same format as a MAPI property tag.</span></span> <span data-ttu-id="1b0ed-194">0 到 15 属性标记的位是该属性的类型。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-194">Bits 0 through 15 of the property tag are the property's type.</span></span> <span data-ttu-id="1b0ed-195">通过 31 16 位是该属性的标识符。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-195">Bits 16 through 31 are the property's identifier.</span></span> <span data-ttu-id="1b0ed-196">属性类型确定应如何读取属性的其余部分。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-196">The property type determines how the rest of the property should be read.</span></span>
  
## <a name="static-value"></a><span data-ttu-id="1b0ed-197">静态值</span><span class="sxs-lookup"><span data-stu-id="1b0ed-197">Static Value</span></span>

<span data-ttu-id="1b0ed-198">某些属性没有值数据，只有联合中的数据。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-198">Some properties have no Value Data and only have data in the union.</span></span> <span data-ttu-id="1b0ed-199">以下属性类型 （其中来自属性标记） 应解释 8 字节属性联合数据，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1b0ed-199">The following property types (which come from the Property Tag) should interpret the 8-byte Property Union data as follows:</span></span>
  
|<span data-ttu-id="1b0ed-200">**属性类型**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-200">**Prop Type**</span></span>|<span data-ttu-id="1b0ed-201">**Union Interpretation 属性**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-201">**Property Union Interpretation**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b0ed-202">PT_I2</span><span class="sxs-lookup"><span data-stu-id="1b0ed-202">PT_I2</span></span>  <br/> |<span data-ttu-id="1b0ed-203">短 int</span><span class="sxs-lookup"><span data-stu-id="1b0ed-203">short int</span></span>  <br/> |
|<span data-ttu-id="1b0ed-204">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="1b0ed-204">PT_LONG</span></span>  <br/> |<span data-ttu-id="1b0ed-205">long</span><span class="sxs-lookup"><span data-stu-id="1b0ed-205">long</span></span>  <br/> |
|<span data-ttu-id="1b0ed-206">PT_R4</span><span class="sxs-lookup"><span data-stu-id="1b0ed-206">PT_R4</span></span>  <br/> |<span data-ttu-id="1b0ed-207">float</span><span class="sxs-lookup"><span data-stu-id="1b0ed-207">float</span></span>  <br/> |
|<span data-ttu-id="1b0ed-208">PT_DOUBLE</span><span class="sxs-lookup"><span data-stu-id="1b0ed-208">PT_DOUBLE</span></span>  <br/> |<span data-ttu-id="1b0ed-209">double</span><span class="sxs-lookup"><span data-stu-id="1b0ed-209">double</span></span>  <br/> |
|<span data-ttu-id="1b0ed-210">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="1b0ed-210">PT_BOOLEAN</span></span>  <br/> |<span data-ttu-id="1b0ed-211">短 int</span><span class="sxs-lookup"><span data-stu-id="1b0ed-211">short int</span></span>  <br/> |
|<span data-ttu-id="1b0ed-212">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="1b0ed-212">PT_SYSTIME</span></span>  <br/> |<span data-ttu-id="1b0ed-213">FILETIME</span><span class="sxs-lookup"><span data-stu-id="1b0ed-213">FILETIME</span></span>  <br/> |
|<span data-ttu-id="1b0ed-214">PT_I8</span><span class="sxs-lookup"><span data-stu-id="1b0ed-214">PT_I8</span></span>  <br/> |<span data-ttu-id="1b0ed-215">LARGE_INTEGER</span><span class="sxs-lookup"><span data-stu-id="1b0ed-215">LARGE_INTEGER</span></span>  <br/> |
   
## <a name="dynamic-values"></a><span data-ttu-id="1b0ed-216">动态值</span><span class="sxs-lookup"><span data-stu-id="1b0ed-216">Dynamic Values</span></span>

<span data-ttu-id="1b0ed-217">其他属性值数据块中有数据后属性标记、 保留的数据和属性值 Union 包含第一个 16 字节。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-217">Other properties have data in a Value Data block after the first 16 bytes that contain the Property Tag, the Reserved Data, and the Property Value Union.</span></span> <span data-ttu-id="1b0ed-218">与静态值、 不同的数据的存储在 8 字节属性值 union 上阅读无关。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-218">Unlike static values, the data that is stored in the 8-byte Property Value union is irrelevant on reading.</span></span> <span data-ttu-id="1b0ed-219">编写时，请确保您具有某些填充这些 8 个字节。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-219">When writing, make sure that you fill these 8 bytes with something.</span></span> <span data-ttu-id="1b0ed-220">但是，8 个字节的内容并不重要。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-220">However, the content of the 8 bytes is not important.</span></span> <span data-ttu-id="1b0ed-221">在动态值属性标记的类型确定如何解释数值数据。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-221">In dynamic values, the property tag's type determines how to interpret the Value Data.</span></span>
  
<span data-ttu-id="1b0ed-222">PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="1b0ed-222">PT_STRING8</span></span> 
  
|<span data-ttu-id="1b0ed-223">**值数据**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-223">**Value Data**</span></span>|<span data-ttu-id="1b0ed-224">**字节数**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-224">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b0ed-225">字节 n 的数目</span><span class="sxs-lookup"><span data-stu-id="1b0ed-225">Number of bytes n</span></span>  <br/> |<span data-ttu-id="1b0ed-226">4</span><span class="sxs-lookup"><span data-stu-id="1b0ed-226">4</span></span>  <br/> |
|<span data-ttu-id="1b0ed-227">字节被解释为 ANSI 字符串 （包括 NULL 终止符）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-227">Bytes to be interpreted as an ANSI string (includes NULL terminator)</span></span>  <br/> |<span data-ttu-id="1b0ed-228">n</span><span class="sxs-lookup"><span data-stu-id="1b0ed-228">n</span></span>  <br/> |
   
<span data-ttu-id="1b0ed-229">PT_CLSID</span><span class="sxs-lookup"><span data-stu-id="1b0ed-229">PT_CLSID</span></span>
  
|<span data-ttu-id="1b0ed-230">**值数据**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-230">**Value Data**</span></span>|<span data-ttu-id="1b0ed-231">**字节数**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-231">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b0ed-232">字节被解释为 GUID</span><span class="sxs-lookup"><span data-stu-id="1b0ed-232">Bytes to be interpreted as a GUID</span></span>  <br/> |<span data-ttu-id="1b0ed-233">16</span><span class="sxs-lookup"><span data-stu-id="1b0ed-233">16</span></span>  <br/> |
|||
   
<span data-ttu-id="1b0ed-234">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="1b0ed-234">PT_BINARY</span></span> 
  
|<span data-ttu-id="1b0ed-235">**值数据**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-235">**Value Data**</span></span>|<span data-ttu-id="1b0ed-236">**字节数**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-236">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b0ed-237">字节 n 的数目</span><span class="sxs-lookup"><span data-stu-id="1b0ed-237">Number of bytes n</span></span>  <br/> |<span data-ttu-id="1b0ed-238">4</span><span class="sxs-lookup"><span data-stu-id="1b0ed-238">4</span></span>  <br/> |
|<span data-ttu-id="1b0ed-239">字节被解释为一个字节数组</span><span class="sxs-lookup"><span data-stu-id="1b0ed-239">Bytes to be interpreted as a byte array</span></span>  <br/> |<span data-ttu-id="1b0ed-240">n</span><span class="sxs-lookup"><span data-stu-id="1b0ed-240">n</span></span>  <br/> |
   
<span data-ttu-id="1b0ed-241">PT_ERROR</span><span class="sxs-lookup"><span data-stu-id="1b0ed-241">PT_ERROR</span></span>
  
|<span data-ttu-id="1b0ed-242">**值数据**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-242">**Value Data**</span></span>|<span data-ttu-id="1b0ed-243">**字节数**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-243">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b0ed-244">字节 n 的数目</span><span class="sxs-lookup"><span data-stu-id="1b0ed-244">Number of bytes n</span></span>  <br/> |<span data-ttu-id="1b0ed-245">4</span><span class="sxs-lookup"><span data-stu-id="1b0ed-245">4</span></span>  <br/> |
|<span data-ttu-id="1b0ed-246">字节被解释为一个字节数组</span><span class="sxs-lookup"><span data-stu-id="1b0ed-246">Bytes to be interpreted as a byte array</span></span>  <br/> |<span data-ttu-id="1b0ed-247">n</span><span class="sxs-lookup"><span data-stu-id="1b0ed-247">n</span></span>  <br/> |
   
<span data-ttu-id="1b0ed-248">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="1b0ed-248">PT_MV_BINARY</span></span>
  
|<span data-ttu-id="1b0ed-249">**值数据**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-249">**Value Data**</span></span>|<span data-ttu-id="1b0ed-250">**字节数**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-250">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b0ed-251">二进制阵列 X 数</span><span class="sxs-lookup"><span data-stu-id="1b0ed-251">Number of binary arrays X</span></span>  <br/> |<span data-ttu-id="1b0ed-252">4</span><span class="sxs-lookup"><span data-stu-id="1b0ed-252">4</span></span>  <br/> |
|<span data-ttu-id="1b0ed-253">一个运行的包含 X 字节二进制数组。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-253">A run of bytes that contains X binary arrays.</span></span> <span data-ttu-id="1b0ed-254">应将每个阵列解释完全一样运行的 PT_BINARY 字节。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-254">Each array should be interpreted exactly like the PT_BINARY byte run.</span></span>  <br/> |<span data-ttu-id="1b0ed-255">变量</span><span class="sxs-lookup"><span data-stu-id="1b0ed-255">Variable</span></span>  <br/> |
   
<span data-ttu-id="1b0ed-256">PT_MV_STRING8 （Outlook 2007 和 Outlook 2010 中，Outlook 2013）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-256">PT_MV_STRING8 (Outlook 2007, Outlook 2010, and Outlook 2013)</span></span>
  
|<span data-ttu-id="1b0ed-257">**值数据**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-257">**Value Data**</span></span>|<span data-ttu-id="1b0ed-258">**字节数**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-258">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b0ed-259">ANSI 字符串 X 数</span><span class="sxs-lookup"><span data-stu-id="1b0ed-259">Number of ANSI strings X</span></span>  <br/> |<span data-ttu-id="1b0ed-260">4</span><span class="sxs-lookup"><span data-stu-id="1b0ed-260">4</span></span>  <br/> |
|<span data-ttu-id="1b0ed-261">一段连续文本的字节，其中包含 X ANSI 字符串。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-261">A run of bytes that contains X ANSI strings.</span></span> <span data-ttu-id="1b0ed-262">应将每个字符串解释完全一样运行的 PT_STRING8 字节。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-262">Each string should be interpreted exactly like the PT_STRING8 byte run.</span></span>  <br/> |<span data-ttu-id="1b0ed-263">变量</span><span class="sxs-lookup"><span data-stu-id="1b0ed-263">Variable</span></span>  <br/> |
   
<span data-ttu-id="1b0ed-264">PT_MV_UNICODE （Outlook 2007、 Outlook 2010 或 Outlook 2013）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-264">PT_MV_UNICODE (Outlook 2007, Outlook 2010, Outlook 2013)</span></span>
  
|<span data-ttu-id="1b0ed-265">**值数据**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-265">**Value Data**</span></span>|<span data-ttu-id="1b0ed-266">**字节数**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-266">**Number of Bytes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b0ed-267">UNICODE 字符串 X 数</span><span class="sxs-lookup"><span data-stu-id="1b0ed-267">Number of UNICODE strings X</span></span>  <br/> |<span data-ttu-id="1b0ed-268">4</span><span class="sxs-lookup"><span data-stu-id="1b0ed-268">4</span></span>  <br/> |
|<span data-ttu-id="1b0ed-269">一段连续文本的字节，其中包含 X UNICODE 字符串。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-269">A run of bytes that contains X UNICODE strings.</span></span> <span data-ttu-id="1b0ed-270">应将每个字符串解释完全一样运行的 PT_UNICODE 字节。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-270">Each string should be interpreted exactly like the PT_UNICODE byte run.</span></span>  <br/> |<span data-ttu-id="1b0ed-271">变量</span><span class="sxs-lookup"><span data-stu-id="1b0ed-271">Variable</span></span>  <br/> |
   
## <a name="significant-properties"></a><span data-ttu-id="1b0ed-272">重要的属性</span><span class="sxs-lookup"><span data-stu-id="1b0ed-272">Significant properties</span></span>

<span data-ttu-id="1b0ed-273">本主题中提到，表示属性的二进制块具有对应的地址簿收件人属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-273">As mentioned previously in this topic, the binary blocks that represent properties have property tags that correspond to properties on address book recipients.</span></span> <span data-ttu-id="1b0ed-274">对于未此处列出的属性，您可以查找属性说明http://msdn.microsoft.com/zh-cn/library/cc433490(EXCHG.80).aspx。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-274">For properties that are not listed here, you can look up the property description at http://msdn.microsoft.com/zh-cn/library/cc433490(EXCHG.80).aspx.</span></span>
  
|<span data-ttu-id="1b0ed-275">**属性名**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-275">**Property Name**</span></span>|<span data-ttu-id="1b0ed-276">**属性标记**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-276">**Property Tag**</span></span>|<span data-ttu-id="1b0ed-277">**说明 （有关详细信息，请参阅 MSDN）**</span><span class="sxs-lookup"><span data-stu-id="1b0ed-277">**Description (see MSDN for more information)**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1b0ed-278">PR_NICK_NAME_W （不在收件人，特定于仅记忆式键入流上传输）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-278">PR_NICK_NAME_W (not transmitted on recipients, specific to autocomplete stream only)</span></span>  <br/> |<span data-ttu-id="1b0ed-279">0x6001001f</span><span class="sxs-lookup"><span data-stu-id="1b0ed-279">0x6001001f</span></span>  <br/> |<span data-ttu-id="1b0ed-280">此属性必须为每个收件人的行中第一个。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-280">This property must be first in each recipient row.</span></span> <span data-ttu-id="1b0ed-281">它功能上相当于收件人行的密钥标识符。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-281">It functionally serves as a key identifier for the recipient row.</span></span>  <br/> |
|<span data-ttu-id="1b0ed-282">PR_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="1b0ed-282">PR_ENTRYID</span></span>  <br/> |<span data-ttu-id="1b0ed-283">0x0FFF0102</span><span class="sxs-lookup"><span data-stu-id="1b0ed-283">0x0FFF0102</span></span>  <br/> |<span data-ttu-id="1b0ed-284">收件人地址簿条目标识符。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-284">The address book entry identifier for the recipient.</span></span>  <br/> |
|<span data-ttu-id="1b0ed-285">PR_DISPLAY_NAME_W</span><span class="sxs-lookup"><span data-stu-id="1b0ed-285">PR_DISPLAY_NAME_W</span></span>  <br/> |<span data-ttu-id="1b0ed-286">0x3001001F</span><span class="sxs-lookup"><span data-stu-id="1b0ed-286">0x3001001F</span></span>  <br/> |<span data-ttu-id="1b0ed-287">收件人的显示名称。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-287">The recipient's display name.</span></span>  <br/> |
|<span data-ttu-id="1b0ed-288">PR_EMAIL_ADDRESS_W</span><span class="sxs-lookup"><span data-stu-id="1b0ed-288">PR_EMAIL_ADDRESS_W</span></span>  <br/> |<span data-ttu-id="1b0ed-289">0x3003001F</span><span class="sxs-lookup"><span data-stu-id="1b0ed-289">0x3003001F</span></span>  <br/> |<span data-ttu-id="1b0ed-290">收件人的电子邮件地址 (例如 johndoe@contoso.com 或 /o = Contoso/OU = Foo/cn = Recipients/cn = johndoe)</span><span class="sxs-lookup"><span data-stu-id="1b0ed-290">The recipient's email address (e.g. johndoe@contoso.com or /o=Contoso/OU=Foo/cn=Recipients/cn=johndoe)</span></span>  <br/> |
|<span data-ttu-id="1b0ed-291">PR_ADDRTYPE_W</span><span class="sxs-lookup"><span data-stu-id="1b0ed-291">PR_ADDRTYPE_W</span></span>  <br/> |<span data-ttu-id="1b0ed-292">0x3002001F</span><span class="sxs-lookup"><span data-stu-id="1b0ed-292">0x3002001F</span></span>  <br/> |<span data-ttu-id="1b0ed-293">收件人的地址类型 （例如 SMTP 或 EX）。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-293">The recipient's address type (e.g. SMTP or EX).</span></span>  <br/> |
|<span data-ttu-id="1b0ed-294">PR_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="1b0ed-294">PR_SEARCH_KEY</span></span>  <br/> |<span data-ttu-id="1b0ed-295">0x300B0102</span><span class="sxs-lookup"><span data-stu-id="1b0ed-295">0x300B0102</span></span>  <br/> |<span data-ttu-id="1b0ed-296">收件人的 MAPI 搜索键。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-296">The recipient's MAPI search key.</span></span>  <br/> |
|<span data-ttu-id="1b0ed-297">PR_SMTP_ADDRESS_W</span><span class="sxs-lookup"><span data-stu-id="1b0ed-297">PR_SMTP_ADDRESS_W</span></span>  <br/> |<span data-ttu-id="1b0ed-298">0x39FE001f</span><span class="sxs-lookup"><span data-stu-id="1b0ed-298">0x39FE001f</span></span>  <br/> |<span data-ttu-id="1b0ed-299">收件人的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-299">The recipient's SMTP address.</span></span>  <br/> |
|<span data-ttu-id="1b0ed-300">PR_DROPDOWN_DISPLAY_NAME_W （不在收件人，特定于仅记忆式键入流上传输）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-300">PR_DROPDOWN_DISPLAY_NAME_W (not transmitted on recipients, specific to autocomplete stream only)</span></span>  <br/> |<span data-ttu-id="1b0ed-301">0X6003001f</span><span class="sxs-lookup"><span data-stu-id="1b0ed-301">0X6003001f</span></span>  <br/> |<span data-ttu-id="1b0ed-302">显示记忆式键入列表中显示字符串。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-302">The display string that appears in the autocomplete list.</span></span>  <br/> |
|<span data-ttu-id="1b0ed-303">PR_NICK_NAME_WEIGHT （不在收件人，特定于仅记忆式键入流上传输）</span><span class="sxs-lookup"><span data-stu-id="1b0ed-303">PR_NICK_NAME_WEIGHT (not transmitted on recipients, specific to autocomplete stream only)</span></span>  <br/> |<span data-ttu-id="1b0ed-304">0x60040003</span><span class="sxs-lookup"><span data-stu-id="1b0ed-304">0x60040003</span></span>  <br/> |<span data-ttu-id="1b0ed-305">此记忆式键入条目的权重。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-305">The weight of this autocomplete entry.</span></span> <span data-ttu-id="1b0ed-306">权重用于确定哪些订单记忆式键入条目时，出现匹配记忆式键入列表。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-306">The weight is used to determine in what order autocomplete entries occur when matching the autocomplete list.</span></span> <span data-ttu-id="1b0ed-307">使用较低的权重项之前将显示具有更高的权重的条目。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-307">Entries with higher weight will show before entries with lower weight.</span></span> <span data-ttu-id="1b0ed-308">完成记忆式键入列表被按此属性。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-308">The complete autocomplete list is sorted by this property.</span></span> <span data-ttu-id="1b0ed-309">权重定期减小随着时间的推移，并增加时用户向此收件人发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-309">The weight periodically decreases over time and increases when the user sends an email to this recipient.</span></span> <span data-ttu-id="1b0ed-310">请参阅有关此属性的详细信息本主题后面的说明。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-310">See the description later in this topic for more information about this property.</span></span>  <br/> |
   
<span data-ttu-id="1b0ed-311">PR_NICK_NAME_WEIGHT</span><span class="sxs-lookup"><span data-stu-id="1b0ed-311">PR_NICK_NAME_WEIGHT</span></span>
  
<span data-ttu-id="1b0ed-312">PR_NICK_NAME_WEIGHT 属性按降序顺序排序的记忆式键入流中的行集并记忆式键入流应始终保留此排序的特征。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-312">The set of rows in the autocomplete stream is sorted in descending order by the PR_NICK_NAME_WEIGHT property and the autocomplete stream should always preserve this sorted characteristic.</span></span> <span data-ttu-id="1b0ed-313">因此，对某一行的权重的任何更改还应确保行的位置保持整个行集的排序的顺序。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-313">Therefore, any changes to a row's weight should also ensure that the row's position maintains the sorted order of the complete set of rows.</span></span> <span data-ttu-id="1b0ed-314">任何行集的新增功能应插入到正确的位置，以维护排序的顺序。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-314">Any additions to the row-set should be inserted to the correct position to maintain the sorted order.</span></span>
  
<span data-ttu-id="1b0ed-315">此权重的最小值是 0x1，最大值是 LONG_MAX。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-315">The minimum value of this weight is 0x1 and the maximum value is LONG_MAX.</span></span> <span data-ttu-id="1b0ed-316">权重的任何其他值都被视为无效。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-316">Any other values for the weight are considered invalid.</span></span>
  
<span data-ttu-id="1b0ed-317">当 Outlook 2007 发送到邮件或解析收件人，它将按 0x2000 提升的收件人的权重。</span><span class="sxs-lookup"><span data-stu-id="1b0ed-317">When Outlook 2007 sends a mail to or resolves a recipient, it will increase that recipient's weight by 0x2000.</span></span>
  

