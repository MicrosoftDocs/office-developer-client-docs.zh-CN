---
title: DataControl 错误代码
TOCTitle: DataControl Error Codes
ms:assetid: d81446e2-aae6-b460-08a3-eae9920dc767
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250089(v=office.15)
ms:contentKeyID: 48548027
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ef139e545fafedd67ca788ebfdc8a8ae86c659e2
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466422"
---
# <a name="datacontrol-error-codes"></a><span data-ttu-id="e9fbf-102">DataControl 错误代码</span><span class="sxs-lookup"><span data-stu-id="e9fbf-102">DataControl Error Codes</span></span>


<span data-ttu-id="e9fbf-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="e9fbf-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="e9fbf-p101">下表列出了 [RDS.DataControl](datacontrol-object-rds.md) 对象的错误代码。其中显示了两个低位字节的正十进制换算值、完整错误代码的负十进制换算值和十六进制值。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-p101">The following table lists the [RDS.DataControl](datacontrol-object-rds.md) object error codes. The positive decimal translation of the low two bytes, the negative decimal translation of the full error code, and the hexadecimal values are shown.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e9fbf-106">RDS.DataControl 错误代码</span><span class="sxs-lookup"><span data-stu-id="e9fbf-106">RDS.DataControl error codes</span></span></p></th>
<th><p><span data-ttu-id="e9fbf-107">编号</span><span class="sxs-lookup"><span data-stu-id="e9fbf-107">Number</span></span></p></th>
<th><p><span data-ttu-id="e9fbf-108">说明</span><span class="sxs-lookup"><span data-stu-id="e9fbf-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9fbf-109"><strong>IDS_AsyncPending</strong></span><span class="sxs-lookup"><span data-stu-id="e9fbf-109"><strong>IDS_AsyncPending</strong></span></span></p></td>
<td><p><span data-ttu-id="e9fbf-110">4107</span><span class="sxs-lookup"><span data-stu-id="e9fbf-110">4107</span></span><br />
<span data-ttu-id="e9fbf-111">-2146824175</span><span class="sxs-lookup"><span data-stu-id="e9fbf-111">-2146824175</span></span><br />
<span data-ttu-id="e9fbf-112">0x800A1011</span><span class="sxs-lookup"><span data-stu-id="e9fbf-112">0x800A1011</span></span></p></td>
<td><p><span data-ttu-id="e9fbf-113">异步操作挂起时不能执行操作。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-113">Operation cannot be performed while async operation is pending.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9fbf-114"><strong>IDS_BadInlineTablegram</strong></span><span class="sxs-lookup"><span data-stu-id="e9fbf-114"><strong>IDS_BadInlineTablegram</strong></span></span></p></td>
<td><p><span data-ttu-id="e9fbf-115">4105</span><span class="sxs-lookup"><span data-stu-id="e9fbf-115">4105</span></span><br />
<span data-ttu-id="e9fbf-116">-2146824183</span><span class="sxs-lookup"><span data-stu-id="e9fbf-116">-2146824183</span></span><br />
<span data-ttu-id="e9fbf-117">0x800A1009</span><span class="sxs-lookup"><span data-stu-id="e9fbf-117">0x800A1009</span></span></p></td>
<td><p><span data-ttu-id="e9fbf-118">内嵌图表错误。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-118">Bad inline tablegram.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9fbf-119"><strong>IDS_CantConnect</strong></span><span class="sxs-lookup"><span data-stu-id="e9fbf-119"><strong>IDS_CantConnect</strong></span></span></p></td>
<td><p><span data-ttu-id="e9fbf-120">4099</span><span class="sxs-lookup"><span data-stu-id="e9fbf-120">4099</span></span><br />
<span data-ttu-id="e9fbf-121">-2146824189</span><span class="sxs-lookup"><span data-stu-id="e9fbf-121">-2146824189</span></span><br />
<span data-ttu-id="e9fbf-122">0x800A1003</span><span class="sxs-lookup"><span data-stu-id="e9fbf-122">0x800A1003</span></span></p></td>
<td><p><span data-ttu-id="e9fbf-123">无法连接到服务器</span><span class="sxs-lookup"><span data-stu-id="e9fbf-123">Cannot connect to server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9fbf-124"><strong>IDS_CantCreateObject</strong></span><span class="sxs-lookup"><span data-stu-id="e9fbf-124"><strong>IDS_CantCreateObject</strong></span></span></p></td>
<td><p><span data-ttu-id="e9fbf-125">4100</span><span class="sxs-lookup"><span data-stu-id="e9fbf-125">4100</span></span><br />
<span data-ttu-id="e9fbf-126">-2146824188</span><span class="sxs-lookup"><span data-stu-id="e9fbf-126">-2146824188</span></span><br />
<span data-ttu-id="e9fbf-127">0x800A1004</span><span class="sxs-lookup"><span data-stu-id="e9fbf-127">0x800A1004</span></span></p></td>
<td><p><span data-ttu-id="e9fbf-128">无法创建业务对象。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-128">Business object cannot be created.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9fbf-129"><strong>IDS_CantFindDataspace</strong></span><span class="sxs-lookup"><span data-stu-id="e9fbf-129"><strong>IDS_CantFindDataspace</strong></span></span></p></td>
<td><p><span data-ttu-id="e9fbf-130">4102</span><span class="sxs-lookup"><span data-stu-id="e9fbf-130">4102</span></span><br />
<span data-ttu-id="e9fbf-131">-2146824186</span><span class="sxs-lookup"><span data-stu-id="e9fbf-131">-2146824186</span></span><br />
<span data-ttu-id="e9fbf-132">0x800A1006</span><span class="sxs-lookup"><span data-stu-id="e9fbf-132">0x800A1006</span></span></p></td>
<td><p><span data-ttu-id="e9fbf-133">Dataspace 属性无效。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-133">Dataspace property is not valid.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9fbf-134"><strong>IDS_CantInvokeMethod</strong></span><span class="sxs-lookup"><span data-stu-id="e9fbf-134"><strong>IDS_CantInvokeMethod</strong></span></span></p></td>
<td><p><span data-ttu-id="e9fbf-135">4101</span><span class="sxs-lookup"><span data-stu-id="e9fbf-135">4101</span></span><br />
<span data-ttu-id="e9fbf-136">-2146824187</span><span class="sxs-lookup"><span data-stu-id="e9fbf-136">-2146824187</span></span><br />
<span data-ttu-id="e9fbf-137">0x800A1005</span><span class="sxs-lookup"><span data-stu-id="e9fbf-137">0x800A1005</span></span></p></td>
<td><p><span data-ttu-id="e9fbf-138">不能对业务对象调用方法。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-138">Method cannot be invoked on business object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9fbf-139"><strong>IDS_CrossDomainWarning</strong></span><span class="sxs-lookup"><span data-stu-id="e9fbf-139"><strong>IDS_CrossDomainWarning</strong></span></span></p></td>
<td><p><span data-ttu-id="e9fbf-140">4112</span><span class="sxs-lookup"><span data-stu-id="e9fbf-140">4112</span></span><br />
<span data-ttu-id="e9fbf-141">-2146824170</span><span class="sxs-lookup"><span data-stu-id="e9fbf-141">-2146824170</span></span><br />
<span data-ttu-id="e9fbf-142">0x800A1016</span><span class="sxs-lookup"><span data-stu-id="e9fbf-142">0x800A1016</span></span></p></td>
<td><p><span data-ttu-id="e9fbf-143">其他域上的数据访问此页。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-143">This page accesses data on another domain.</span></span> <span data-ttu-id="e9fbf-144">若要允许此吗？</span><span class="sxs-lookup"><span data-stu-id="e9fbf-144">Do you want to allow this?</span></span> <span data-ttu-id="e9fbf-145">要避免出现此消息在 Internet Explorer 中的，可以安全网站添加到受信任的站点区域上的<strong>Internet 选项</strong>对话框的<strong>安全</strong>选项卡。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-145">To avoid this message in Internet Explorer, you can add a secure website to your Trusted Sites zone on the <strong>Security</strong> tab of the <strong>Internet Options</strong> dialog box.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9fbf-146"><strong>IDS_InvalidADCClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e9fbf-146"><strong>IDS_InvalidADCClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e9fbf-147">4106</span><span class="sxs-lookup"><span data-stu-id="e9fbf-147">4106</span></span><br />
<span data-ttu-id="e9fbf-148">-2146824176</span><span class="sxs-lookup"><span data-stu-id="e9fbf-148">-2146824176</span></span><br />
<span data-ttu-id="e9fbf-149">0x800A1010</span><span class="sxs-lookup"><span data-stu-id="e9fbf-149">0x800A1010</span></span></p></td>
<td><p><span data-ttu-id="e9fbf-150">RDS 客户端版本无效 — 客户端是较服务器。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-150">Invalid RDS Client Version — Client is newer than server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9fbf-151"><strong>IDS_INVALIDARG</strong></span><span class="sxs-lookup"><span data-stu-id="e9fbf-151"><strong>IDS_INVALIDARG</strong></span></span></p></td>
<td><p><span data-ttu-id="e9fbf-152">5376</span><span class="sxs-lookup"><span data-stu-id="e9fbf-152">5376</span></span><br />
<span data-ttu-id="e9fbf-153">-2147019520</span><span class="sxs-lookup"><span data-stu-id="e9fbf-153">-2147019520</span></span><br />
<span data-ttu-id="e9fbf-154">0x80071500</span><span class="sxs-lookup"><span data-stu-id="e9fbf-154">0x80071500</span></span></p></td>
<td><p><span data-ttu-id="e9fbf-155">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-155">One or more arguments are invalid.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9fbf-156"><strong>IDS_InvalidBindings</strong></span><span class="sxs-lookup"><span data-stu-id="e9fbf-156"><strong>IDS_InvalidBindings</strong></span></span></p></td>
<td><p><span data-ttu-id="e9fbf-157">4097</span><span class="sxs-lookup"><span data-stu-id="e9fbf-157">4097</span></span><br />
<span data-ttu-id="e9fbf-158">-2146824191</span><span class="sxs-lookup"><span data-stu-id="e9fbf-158">-2146824191</span></span><br />
<span data-ttu-id="e9fbf-159">0x800A1001</span><span class="sxs-lookup"><span data-stu-id="e9fbf-159">0x800A1001</span></span></p></td>
<td><p><span data-ttu-id="e9fbf-160">绑定属性中存在错误。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-160">Error in bindings property.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9fbf-161"><strong>IDS_InvalidParam</strong></span><span class="sxs-lookup"><span data-stu-id="e9fbf-161"><strong>IDS_InvalidParam</strong></span></span></p></td>
<td><p><span data-ttu-id="e9fbf-162">4110</span><span class="sxs-lookup"><span data-stu-id="e9fbf-162">4110</span></span><br />
<span data-ttu-id="e9fbf-163">-2146824172</span><span class="sxs-lookup"><span data-stu-id="e9fbf-163">-2146824172</span></span><br />
<span data-ttu-id="e9fbf-164">0x800A1014</span><span class="sxs-lookup"><span data-stu-id="e9fbf-164">0x800A1014</span></span></p></td>
<td><p><span data-ttu-id="e9fbf-165">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-165">One or more arguments are invalid.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9fbf-166"><strong>IDS_NOINTERFACE</strong></span><span class="sxs-lookup"><span data-stu-id="e9fbf-166"><strong>IDS_NOINTERFACE</strong></span></span></p></td>
<td><p><span data-ttu-id="e9fbf-167">5377</span><span class="sxs-lookup"><span data-stu-id="e9fbf-167">5377</span></span><br />
<span data-ttu-id="e9fbf-168">-2147019519</span><span class="sxs-lookup"><span data-stu-id="e9fbf-168">-2147019519</span></span><br />
<span data-ttu-id="e9fbf-169">0x80071501</span><span class="sxs-lookup"><span data-stu-id="e9fbf-169">0x80071501</span></span></p></td>
<td><p><span data-ttu-id="e9fbf-170">不支持这类接口。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-170">No such interface is supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9fbf-171"><strong>IDS_NotReentrant</strong></span><span class="sxs-lookup"><span data-stu-id="e9fbf-171"><strong>IDS_NotReentrant</strong></span></span></p></td>
<td><p><span data-ttu-id="e9fbf-172">4111</span><span class="sxs-lookup"><span data-stu-id="e9fbf-172">4111</span></span><br />
<span data-ttu-id="e9fbf-173">-2146824171</span><span class="sxs-lookup"><span data-stu-id="e9fbf-173">-2146824171</span></span><br />
<span data-ttu-id="e9fbf-174">0x800A1015</span><span class="sxs-lookup"><span data-stu-id="e9fbf-174">0x800A1015</span></span></p></td>
<td><p><span data-ttu-id="e9fbf-175">事件处理程序仍在处理期间，不能执行请求。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-175">Request cannot be executed while the event handler is still processing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9fbf-176"><strong>IDS_ObjectNotSafe</strong></span><span class="sxs-lookup"><span data-stu-id="e9fbf-176"><strong>IDS_ObjectNotSafe</strong></span></span></p></td>
<td><p><span data-ttu-id="e9fbf-177">4103</span><span class="sxs-lookup"><span data-stu-id="e9fbf-177">4103</span></span><br />
<span data-ttu-id="e9fbf-178">-2146824185</span><span class="sxs-lookup"><span data-stu-id="e9fbf-178">-2146824185</span></span><br />
<span data-ttu-id="e9fbf-179">0x800A1007</span><span class="sxs-lookup"><span data-stu-id="e9fbf-179">0x800A1007</span></span></p></td>
<td><p><span data-ttu-id="e9fbf-180">此计算机上的安全设置禁止创建业务对象。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-180">Safety settings on this computer prohibit creation of business object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9fbf-181"><strong>IDS_RecordsetNotOpen</strong></span><span class="sxs-lookup"><span data-stu-id="e9fbf-181"><strong>IDS_RecordsetNotOpen</strong></span></span></p></td>
<td><p><span data-ttu-id="e9fbf-182">4109</span><span class="sxs-lookup"><span data-stu-id="e9fbf-182">4109</span></span><br />
<span data-ttu-id="e9fbf-183">-2146824173</span><span class="sxs-lookup"><span data-stu-id="e9fbf-183">-2146824173</span></span><br />
<span data-ttu-id="e9fbf-184">0x800A1013</span><span class="sxs-lookup"><span data-stu-id="e9fbf-184">0x800A1013</span></span></p></td>
<td><p><span data-ttu-id="e9fbf-185">未打开 <strong>Recordset</strong>。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-185"><strong>Recordset</strong> is not open.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9fbf-186"><strong>IDS_ResetInvalidField</strong></span><span class="sxs-lookup"><span data-stu-id="e9fbf-186"><strong>IDS_ResetInvalidField</strong></span></span></p></td>
<td><p><span data-ttu-id="e9fbf-187">4108</span><span class="sxs-lookup"><span data-stu-id="e9fbf-187">4108</span></span><br />
<span data-ttu-id="e9fbf-188">-2146824174</span><span class="sxs-lookup"><span data-stu-id="e9fbf-188">-2146824174</span></span><br />
<span data-ttu-id="e9fbf-189">0x800A1012</span><span class="sxs-lookup"><span data-stu-id="e9fbf-189">0x800A1012</span></span></p></td>
<td><p><span data-ttu-id="e9fbf-190">在 <strong>SortColumn</strong> 或 <strong>FilterColumn</strong> 中指定的列不存在。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-190">Column specified in <strong>SortColumn</strong> or <strong>FilterColumn</strong> does not exist.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9fbf-191"><strong>IDS_RowsetNotUpdateable</strong></span><span class="sxs-lookup"><span data-stu-id="e9fbf-191"><strong>IDS_RowsetNotUpdateable</strong></span></span></p></td>
<td><p><span data-ttu-id="e9fbf-192">4104</span><span class="sxs-lookup"><span data-stu-id="e9fbf-192">4104</span></span><br />
<span data-ttu-id="e9fbf-193">-2146824184</span><span class="sxs-lookup"><span data-stu-id="e9fbf-193">-2146824184</span></span><br />
<span data-ttu-id="e9fbf-194">0x800A1008</span><span class="sxs-lookup"><span data-stu-id="e9fbf-194">0x800A1008</span></span></p></td>
<td><p><span data-ttu-id="e9fbf-195">行集不可更新。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-195">Rowset not updateable.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9fbf-196"><strong>IDS_UnexpectedError</strong></span><span class="sxs-lookup"><span data-stu-id="e9fbf-196"><strong>IDS_UnexpectedError</strong></span></span></p></td>
<td><p><span data-ttu-id="e9fbf-197">4351</span><span class="sxs-lookup"><span data-stu-id="e9fbf-197">4351</span></span><br />
<span data-ttu-id="e9fbf-198">-2146823937</span><span class="sxs-lookup"><span data-stu-id="e9fbf-198">-2146823937</span></span><br />
<span data-ttu-id="e9fbf-199">0x800A10FF</span><span class="sxs-lookup"><span data-stu-id="e9fbf-199">0x800A10FF</span></span></p></td>
<td><p><span data-ttu-id="e9fbf-200">意外的错误。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-200">Unexpected error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9fbf-201"><strong>IDS_UpdatesFailed</strong></span><span class="sxs-lookup"><span data-stu-id="e9fbf-201"><strong>IDS_UpdatesFailed</strong></span></span></p></td>
<td><p><span data-ttu-id="e9fbf-202">4098</span><span class="sxs-lookup"><span data-stu-id="e9fbf-202">4098</span></span><br />
<span data-ttu-id="e9fbf-203">-2146824190</span><span class="sxs-lookup"><span data-stu-id="e9fbf-203">-2146824190</span></span><br />
<span data-ttu-id="e9fbf-204">0x800A1002</span><span class="sxs-lookup"><span data-stu-id="e9fbf-204">0x800A1002</span></span></p></td>
<td><p><span data-ttu-id="e9fbf-205">无法更新数据库。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-205">Unable to update database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9fbf-206"><strong>IDS_URLMONNotFound</strong></span><span class="sxs-lookup"><span data-stu-id="e9fbf-206"><strong>IDS_URLMONNotFound</strong></span></span></p></td>
<td><p><span data-ttu-id="e9fbf-207">4119</span><span class="sxs-lookup"><span data-stu-id="e9fbf-207">4119</span></span><br />
<span data-ttu-id="e9fbf-208">-2146824169</span><span class="sxs-lookup"><span data-stu-id="e9fbf-208">-2146824169</span></span><br />
<span data-ttu-id="e9fbf-209">0x800A1017</span><span class="sxs-lookup"><span data-stu-id="e9fbf-209">0x800A1017</span></span></p></td>
<td><p><span data-ttu-id="e9fbf-210">DataControl <strong>URL</strong> 属性需要系统文件 Urlmon.dll，但找不到该文件。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-210">DataControl <strong>URL</strong> property requires the system file Urlmon.dll, which cannot be found.</span></span></p></td>
</tr>
</tbody>
</table>

