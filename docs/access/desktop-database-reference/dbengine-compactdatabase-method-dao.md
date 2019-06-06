---
title: DBEngine.CompactDatabase 方法 (DAO)
TOCTitle: CompactDatabase Method
ms:assetid: 03f3a156-005a-4b71-81b0-598f326f7d42
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844821(v=office.15)
ms:contentKeyID: 48542997
ms.date: 10/24/2016
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052936
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: b50cb0453df1fa357fbd0b089af2e74fdd4b4c1e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294335"
---
# <a name="dbenginecompactdatabase-method-dao"></a><span data-ttu-id="552dd-102">DBEngine.CompactDatabase 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="552dd-102">DBEngine.CompactDatabase method (DAO)</span></span>

<span data-ttu-id="552dd-103">**适用于：** Access 2013 | Access 2016</span><span class="sxs-lookup"><span data-stu-id="552dd-103">**Applies to:** Access 2013 | Access 2016</span></span>

<span data-ttu-id="552dd-104">复制并压缩关闭的数据库，使您可以选择更改其版本、整理顺序和加密设置。</span><span class="sxs-lookup"><span data-stu-id="552dd-104">Copies and compacts a closed database, and gives you the option of changing its version, collating order, and encryption.</span></span> <span data-ttu-id="552dd-105">（仅适用于 Microsoft Access 工作区。</span><span class="sxs-lookup"><span data-stu-id="552dd-105">(Microsoft Access workspaces only).</span></span>

> [!NOTE]
> <span data-ttu-id="552dd-106">使用加密的链接表来执行操作、更新和 SQL 查询 [例如 SQL UPDATE 语句 (CurrentDb.Execute "UPDATE...")] 时，你必须提供加密密钥。</span><span class="sxs-lookup"><span data-stu-id="552dd-106">When using encrypted linked tables for action, update, and SQL queries [such as a SQL UPDATE statement (CurrentDb.Execute "UPDATE...")], you must supply the encryption key.</span></span> <span data-ttu-id="552dd-107">此外，链接表对加密密钥有 19 字符的限制。</span><span class="sxs-lookup"><span data-stu-id="552dd-107">Also, linked tables have a 19-character limit for the encryption key.</span></span> <span data-ttu-id="552dd-108">请参阅本主题结尾的**加密的链接表**部分。</span><span class="sxs-lookup"><span data-stu-id="552dd-108">See the **Encrypted linked tables** section at the end of this topic.</span></span>

## <a name="syntax"></a><span data-ttu-id="552dd-109">语法</span><span class="sxs-lookup"><span data-stu-id="552dd-109">Syntax</span></span>

<span data-ttu-id="552dd-110">*expression* .CompactDatabase(***SrcName***, ***DstName***, ***DstLocale***, ***Options***, ***password***)</span><span class="sxs-lookup"><span data-stu-id="552dd-110">CompactDatabase(\*\*\*\*SrcName\*\*\*\*, ***DstName***, ***DstLocale, \*\*\*\*\*\*Options, \*\*\*\*\*\*password***)</span></span>

<span data-ttu-id="552dd-111">*expression*一个返回 **DBEngine** 对象的表达式。</span><span class="sxs-lookup"><span data-stu-id="552dd-111">*expression*  An expression that returns a **DBEngine** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="552dd-112">参数</span><span class="sxs-lookup"><span data-stu-id="552dd-112">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="552dd-113">名称</span><span class="sxs-lookup"><span data-stu-id="552dd-113">Name</span></span></p></th>
<th><p><span data-ttu-id="552dd-114">必需/可选</span><span class="sxs-lookup"><span data-stu-id="552dd-114">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="552dd-115">数据类型</span><span class="sxs-lookup"><span data-stu-id="552dd-115">Data type</span></span></p></th>
<th><p><span data-ttu-id="552dd-116">说明</span><span class="sxs-lookup"><span data-stu-id="552dd-116">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="552dd-117"><em>SrcName</em></span><span class="sxs-lookup"><span data-stu-id="552dd-117"><em>SrcName</em></span></span></p></td>
<td><p><span data-ttu-id="552dd-118">必需</span><span class="sxs-lookup"><span data-stu-id="552dd-118">Required</span></span></p></td>
<td><p><span data-ttu-id="552dd-119"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-119"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-120">识别现有的已关闭数据库。</span><span class="sxs-lookup"><span data-stu-id="552dd-120">Identifies an existing, closed database.</span></span> <span data-ttu-id="552dd-121">可以是完整路径和文件名，例如 &quot;C:\db1.mdb&quot;。</span><span class="sxs-lookup"><span data-stu-id="552dd-121">It can be a full path and file name, such as "C:\db1.mdb".</span></span> <span data-ttu-id="552dd-122">如果文件名称有扩展名，必须指定。</span><span class="sxs-lookup"><span data-stu-id="552dd-122">If the file name has an extension, you must specify it.</span></span> <span data-ttu-id="552dd-123">如果网络支持的话，也可以指定网络路径，例如&quot;\\server1\share1\dir1\db1.mdb&quot;</span><span class="sxs-lookup"><span data-stu-id="552dd-123">If your network supports it, you can also specify a network path, such as "\\server1\share1\dir1\db1.mdb"</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="552dd-124"><em>DstName</em></span><span class="sxs-lookup"><span data-stu-id="552dd-124"><em>DstName</em></span></span></p></td>
<td><p><span data-ttu-id="552dd-125">必需</span><span class="sxs-lookup"><span data-stu-id="552dd-125">Required</span></span></p></td>
<td><p><span data-ttu-id="552dd-126"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-126"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-127">您要创建的压缩数据库的文件名（和路径）。</span><span class="sxs-lookup"><span data-stu-id="552dd-127">the file name (and path) of the compacted database that you're creating.</span></span> <span data-ttu-id="552dd-128">还可以指定网络路径。</span><span class="sxs-lookup"><span data-stu-id="552dd-128">You can also specify a network path.</span></span> <span data-ttu-id="552dd-129">不能使用此参数来指定与 SrcName 相同的数据库文件。</span><span class="sxs-lookup"><span data-stu-id="552dd-129">You can't use this  argument to specify the same database file as SrcName.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="552dd-130"><em>DstLocale</em></span><span class="sxs-lookup"><span data-stu-id="552dd-130"><em>DstLocale</em></span></span></p></td>
<td><p><span data-ttu-id="552dd-131">可选</span><span class="sxs-lookup"><span data-stu-id="552dd-131">Optional</span></span></p></td>
<td><p><span data-ttu-id="552dd-132"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-132"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-133">指定用于创建 DstName 整理顺序的字符串表达式，如“备注”中所指定的。</span><span class="sxs-lookup"><span data-stu-id="552dd-133">A string expression that specifies a collating order for creating DstName, as specified in Remarks.</span></span></p>
<ul>
<li><p><span data-ttu-id="552dd-134">如果省略此参数，则 DstName 区域设置与 SrcName 相同。</span><span class="sxs-lookup"><span data-stu-id="552dd-134">If you omit this argument, the locale of DstName is the same as SrcName.</span></span></p></li>
<li><p><span data-ttu-id="552dd-135">还可以通过将密码字符串（以&quot;;pwd=&quot;开头）与 DstLocale 参数中的常量相连（例如 dbLangSpanish &amp; &quot;;pwd=NewPassword&quot;）创建 DstName 的密码。</span><span class="sxs-lookup"><span data-stu-id="552dd-135">You can also create a password for DstName by concatenating the password string (starting with ";pwd=") with a constant in the DstLocale argument, like this: dbLangSpanish & ";pwd=NewPassword".</span></span></p></li>
<li><p><span data-ttu-id="552dd-136">如果要使用与 SrcName 相同的 DstLocale（默认值），但指定新密码，则只需输入 DstLocale 的密码字符串即可：&quot;;pwd=NewPassword&quot;</span><span class="sxs-lookup"><span data-stu-id="552dd-136">If you want to use the same DstLocale as SrcName (the default value), but specify a new password, simply enter a password string for DstLocale: ";pwd=NewPassword"</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="552dd-137"><em>选项</em></span><span class="sxs-lookup"><span data-stu-id="552dd-137"><em>Options</em></span></span></p></td>
<td><p><span data-ttu-id="552dd-138">可选</span><span class="sxs-lookup"><span data-stu-id="552dd-138">Optional</span></span></p></td>
<td><p><span data-ttu-id="552dd-139"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-139"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-p105">可选。一个常量或常量的组合，用于指示一个或多个选项（根据“说明”中的指定）。可通过对相应的常量求和来组合选项。</span><span class="sxs-lookup"><span data-stu-id="552dd-p105">Optional. A constant or combination of constants that indicates one or more options, as specified in Remarks. You can combine options by summing the corresponding constants.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="552dd-143"><em>password</em></span><span class="sxs-lookup"><span data-stu-id="552dd-143"><em>Password</em></span></span></p></td>
<td><p><span data-ttu-id="552dd-144">可选</span><span class="sxs-lookup"><span data-stu-id="552dd-144">Optional</span></span></p></td>
<td><p><span data-ttu-id="552dd-145"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-145"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-146">包含加密密钥的字符串表达式（若数据库加密）。</span><span class="sxs-lookup"><span data-stu-id="552dd-146">A string expression containing an encryption key, if the database is encrypted.</span></span> <span data-ttu-id="552dd-147">字符串&quot;; pwd =&quot;必须位于实际密码之前。</span><span class="sxs-lookup"><span data-stu-id="552dd-147">The string &quot;;pwd=&quot; must precede the actual password.</span></span> <span data-ttu-id="552dd-148">如果在 DstLocale 中包括密码设置，则忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="552dd-148">If you include a password setting in DstLocale, this setting is ignored.</span></span></p><p><span data-ttu-id="552dd-149"><strong>注释</strong>：这是已弃用的参数, 不支持 .ACCDB 格式。</span><span class="sxs-lookup"><span data-stu-id="552dd-149"><strong>NOTE</strong>: This is deprecated parameter and is not supported in .ACCDB format.</span></span> <span data-ttu-id="552dd-150">要加密 .ACCDB 文件，请使用 "pwd =" 选项字符串。</span><span class="sxs-lookup"><span data-stu-id="552dd-150">To encrypt an .ACCDB file, use the "pwd=" option string.</span></span> <span data-ttu-id="552dd-151">使用混合大小写字母、数字和符号的强密码。</span><span class="sxs-lookup"><span data-stu-id="552dd-151">Use strong passwords that combine upper- and lowercase letters, numbers, and symbols.</span></span> <span data-ttu-id="552dd-152">弱密码不混合使用这些元素。</span><span class="sxs-lookup"><span data-stu-id="552dd-152">Weak passwords don't mix these elements.</span></span> <span data-ttu-id="552dd-153">例如，强密码：Y6dh!et5。</span><span class="sxs-lookup"><span data-stu-id="552dd-153">Strong password: Y6dh!et5.</span></span> <span data-ttu-id="552dd-154">弱密码：House27。</span><span class="sxs-lookup"><span data-stu-id="552dd-154">Weak password: House27.</span></span> <span data-ttu-id="552dd-155">请使用可以记住的强密码，这样就不必记录密码了。</span><span class="sxs-lookup"><span data-stu-id="552dd-155">Use a strong password that you can remember so that you don't have to write it down.</span></span></p>
</td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="552dd-156">说明</span><span class="sxs-lookup"><span data-stu-id="552dd-156">Remarks</span></span>

<span data-ttu-id="552dd-157">可以使用 DstLocale 参数的下列常量之一来指定用于文本字符串比较的**CollatingOrder**属性。</span><span class="sxs-lookup"><span data-stu-id="552dd-157">You can use one of the following constants for the DstLocale argument to specify the **CollatingOrder** property for string comparisons of text.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="552dd-158">常量</span><span class="sxs-lookup"><span data-stu-id="552dd-158">Constant</span></span></p></th>
<th><p><span data-ttu-id="552dd-159">整理顺序</span><span class="sxs-lookup"><span data-stu-id="552dd-159">Collating order</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="552dd-160"><strong>dbLangGeneral</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-160"><strong>dbLangGeneral</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-161">英语、德语、法语、葡萄牙语、意大利语和现代西班牙语</span><span class="sxs-lookup"><span data-stu-id="552dd-161">English, German, French, Portuguese, Italian, and Modern Spanish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="552dd-162"><strong>dbLangArabic</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-162"><strong>dbLangArabic</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-163">阿拉伯语</span><span class="sxs-lookup"><span data-stu-id="552dd-163">Arabic</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="552dd-164"><strong>dbLangChineseSimplified</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-164"><strong>dbLangChineseSimplified</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-165">简体中文</span><span class="sxs-lookup"><span data-stu-id="552dd-165">Simplified Chinese</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="552dd-166"><strong>dbLangChineseTraditional</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-166"><strong>dbLangChineseTraditional</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-167">繁体中文</span><span class="sxs-lookup"><span data-stu-id="552dd-167">Traditional Chinese</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="552dd-168"><strong>dbLangCyrillic</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-168"><strong>dbLangCyrillic</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-169">俄语</span><span class="sxs-lookup"><span data-stu-id="552dd-169">Russian</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="552dd-170"><strong>dbLangCzech</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-170"><strong>dbLangCzech</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-171">捷克语</span><span class="sxs-lookup"><span data-stu-id="552dd-171">Czech</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="552dd-172"><strong>dbLangDutch</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-172"><strong>dbLangDutch</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-173">荷兰语</span><span class="sxs-lookup"><span data-stu-id="552dd-173">Dutch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="552dd-174"><strong>dbLangGreek</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-174"><strong>dbLangGreek</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-175">希腊语</span><span class="sxs-lookup"><span data-stu-id="552dd-175">Greek</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="552dd-176"><strong>dbLangHebrew</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-176"><strong>dbLangHebrew</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-177">希伯来语</span><span class="sxs-lookup"><span data-stu-id="552dd-177">Hebrew</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="552dd-178"><strong>dbLangHungarian</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-178"><strong>dbLangHungarian</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-179">匈牙利语</span><span class="sxs-lookup"><span data-stu-id="552dd-179">Hungarian</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="552dd-180"><strong>dbLangIcelandic</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-180"><strong>dbLangIcelandic</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-181">冰岛语</span><span class="sxs-lookup"><span data-stu-id="552dd-181">Icelandic</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="552dd-182"><strong>dbLangJapanese</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-182"><strong>dbLangJapanese</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-183">日语</span><span class="sxs-lookup"><span data-stu-id="552dd-183">Japanese</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="552dd-184"><strong>dbLangKorean</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-184"><strong>dbLangKorean</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-185">朝鲜语</span><span class="sxs-lookup"><span data-stu-id="552dd-185">Korean</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="552dd-186"><strong>dbLangNordic</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-186"><strong>dbLangNordic</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-187">北欧语言（仅适用于 Microsoft Jet 数据库引擎 1.0 版）</span><span class="sxs-lookup"><span data-stu-id="552dd-187">Nordic languages (Microsoft Jet database engine version 1.0 only)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="552dd-188"><strong>dbLangNorwDan</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-188"><strong>dbLangNorwDan</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-189">挪威语和丹麦语</span><span class="sxs-lookup"><span data-stu-id="552dd-189">Norwegian and Danish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="552dd-190"><strong>dbLangPolish</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-190"><strong>dbLangPolish</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-191">波兰语</span><span class="sxs-lookup"><span data-stu-id="552dd-191">Polish</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="552dd-192"><strong>dbLangSlovenian</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-192"><strong>dbLangSlovenian</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-193">斯洛文尼亚语</span><span class="sxs-lookup"><span data-stu-id="552dd-193">Slovenian</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="552dd-194"><strong>dbLangSpanish</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-194"><strong>dbLangSpanish</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-195">传统西班牙语</span><span class="sxs-lookup"><span data-stu-id="552dd-195">Traditional Spanish</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="552dd-196"><strong>dbLangSwedFin</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-196"><strong>dbLangSwedFin</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-197">瑞典语和芬兰语</span><span class="sxs-lookup"><span data-stu-id="552dd-197">Swedish and Finnish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="552dd-198"><strong>dbLangThai</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-198"><strong>dbLangThai</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-199">泰语</span><span class="sxs-lookup"><span data-stu-id="552dd-199">Thai</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="552dd-200"><strong>dbLangTurkish</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-200"><strong>dbLangTurkish</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-201">土耳其语</span><span class="sxs-lookup"><span data-stu-id="552dd-201">Turkish</span></span></p></td>
</tr>
</tbody>
</table>

<br/>

<span data-ttu-id="552dd-202">可以在 options 参数中使用以下常量之一来指定在压缩数据库时对数据库进行加密还是解密。</span><span class="sxs-lookup"><span data-stu-id="552dd-202">You can use one of the following constants in the options argument to specify whether to encrypt or to decrypt the database while it's compacted.</span></span>

> [!NOTE]
> <span data-ttu-id="552dd-203">常量 dbEncrypt 和 dbDecrypt 已弃用，不支持 .ACCDB 文件格式。</span><span class="sxs-lookup"><span data-stu-id="552dd-203">The constants dbEncrypt and dbDecrypt are deprecated and not supported in .ACCDB file formats.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="552dd-204">常量</span><span class="sxs-lookup"><span data-stu-id="552dd-204">Constant</span></span></p></th>
<th><p><span data-ttu-id="552dd-205">说明</span><span class="sxs-lookup"><span data-stu-id="552dd-205">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="552dd-206"><strong>dbEncrypt</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-206"><strong>dbEncrypt</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-207">压缩时加密数据库。</span><span class="sxs-lookup"><span data-stu-id="552dd-207">Encrypt the database while compacting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="552dd-208"><strong>dbDecrypt</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-208"><strong>dbDecrypt</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-209">压缩时解密数据库。</span><span class="sxs-lookup"><span data-stu-id="552dd-209">Decrypt the database while compacting.</span></span></p></td>
</tr>
</tbody>
</table>

<br/>

<span data-ttu-id="552dd-210">如果省略加密常量或同时包括 **dbDecrypt** 和 **dbEncrypt**，DstName 将与 SrcName 具有相同的加密。</span><span class="sxs-lookup"><span data-stu-id="552dd-210">If you omit an encryption constant or if you include both dbDecrypt and dbEncrypt, DstName will have the same encryption as SrcName.</span></span>

<span data-ttu-id="552dd-211">可以在 options 参数中使用下列常量之一来指定压缩数据库的数据格式的版本。</span><span class="sxs-lookup"><span data-stu-id="552dd-211">You can use one of the following constants in the  options argument to specify the version of the data format for the compacted database.</span></span> <span data-ttu-id="552dd-212">此常量仅影响 DstName 的数据格式的版本，而不会影响任何 Microsoft Access 定义的对象（例如窗体和报表）的版本。</span><span class="sxs-lookup"><span data-stu-id="552dd-212">This constant affects only the version of the data format of DstName and doesn't affect the version of any Microsoft Access-defined objects, such as forms and reports.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="552dd-213">常量</span><span class="sxs-lookup"><span data-stu-id="552dd-213">Constant</span></span></p></th>
<th><p><span data-ttu-id="552dd-214">说明</span><span class="sxs-lookup"><span data-stu-id="552dd-214">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="552dd-215"><strong>dbVersion10</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-215"><strong>dbVersion10</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-216">在压缩时创建一个使用 Microsoft Jet 数据库引擎 1.0 版文件格式的数据库。</span><span class="sxs-lookup"><span data-stu-id="552dd-216">Creates a database that uses the Microsoft Jet database engine version 1.0 file format while compacting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="552dd-217"><strong>dbVersion11</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-217"><strong>dbVersion11</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-218">在压缩时创建一个使用 Microsoft Jet 数据库引擎 1.1 版文件格式的数据库。</span><span class="sxs-lookup"><span data-stu-id="552dd-218">Creates a database that uses the Microsoft Jet database engine version 1.1 file format while compacting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="552dd-219"><strong>dbVersion20</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-219"><strong>dbVersion20</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-220">在压缩时创建一个使用 Microsoft Jet 数据库引擎 2.0 版文件格式的数据库。</span><span class="sxs-lookup"><span data-stu-id="552dd-220">Creates a database that uses the Microsoft Jet database engine version 2.0 file format while compacting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="552dd-221"><strong>dbVersion30</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-221"><strong>dbVersion30</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-222">在压缩时创建一个使用 Microsoft Jet 数据库引擎 3.0 版文件格式的数据库（与 3.5 版兼容）。</span><span class="sxs-lookup"><span data-stu-id="552dd-222">Creates a database that uses the Microsoft Jet database engine version 3.0 file format (compatible with version 3.5) while compacting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="552dd-223"><strong>dbVersion40</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-223"><strong>dbVersion40</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-224">在压缩时创建一个使用 Microsoft Jet 数据库引擎 4.0 版文件格式的数据库。</span><span class="sxs-lookup"><span data-stu-id="552dd-224">Creates a database that uses the Microsoft Jet database engine version 4.0 file format while compacting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="552dd-225"><strong>dbVersion120</strong></span><span class="sxs-lookup"><span data-stu-id="552dd-225"><strong>dbVersion120</strong></span></span></p></td>
<td><p><span data-ttu-id="552dd-226">创建一个压缩时使用 Microsoft Access 数据库引擎版本 12.0 文件格式的数据库。</span><span class="sxs-lookup"><span data-stu-id="552dd-226">Creates a database that uses the Microsoft Access database engine version 12.0 file format while compacting.</span></span></p></td>
</tr>
</tbody>
</table>

<br/>

<span data-ttu-id="552dd-227">只能指定一个版本常量。</span><span class="sxs-lookup"><span data-stu-id="552dd-227">You can specify only one version constant.</span></span> <span data-ttu-id="552dd-228">如果省略版本常量，DstName 将与 SrcName 具有相同的版本。</span><span class="sxs-lookup"><span data-stu-id="552dd-228">If you omit a version constant,  DstName will have the same version as  SrcName.</span></span> <span data-ttu-id="552dd-229">只能将 DstName 压缩为等于或高于 SrcName 版本的版本。</span><span class="sxs-lookup"><span data-stu-id="552dd-229">You can compact  DstName only to a version that is the same or later than that of  SrcName.</span></span>

<span data-ttu-id="552dd-p110">更改数据库中的数据时，数据库文件中会产生碎片，并使用多于所需量的磁盘空间。您可以定期使用 **CompactDatabase** 方法来压缩数据库，对数据库文件进行碎片整理。压缩的数据库通常更小且运行速度更快。在复制和压缩数据库时，还可以更改整理顺序、加密或数据格式的版本。</span><span class="sxs-lookup"><span data-stu-id="552dd-p110">As you change data in a database, the database file can become fragmented and use more disk space than is necessary. Periodically, you can use the **CompactDatabase** method to compact your database to defragment the database file. The compacted database is usually smaller and often runs faster. You can also change the collating order, the encryption, or the version of the data format while you copy and compact the database.</span></span>

<span data-ttu-id="552dd-234">压缩 SrcName 之前，必须关闭它。</span><span class="sxs-lookup"><span data-stu-id="552dd-234">You must close  SrcName before you compact it.</span></span> <span data-ttu-id="552dd-235">在多用户环境中，在你压缩 SrcName 时，其他用户不能打开它。</span><span class="sxs-lookup"><span data-stu-id="552dd-235">In a multiuser environment, other users can't have  SrcName open while you're compacting it.</span></span> <span data-ttu-id="552dd-236">如果 SrcName 未关闭或者不能独占使用，将会发生错误。</span><span class="sxs-lookup"><span data-stu-id="552dd-236">If  SrcName isn't closed or isn't available for exclusive use, an error occurs.</span></span>

<span data-ttu-id="552dd-237">由于 **CompactDatabase** 会创建数据库的副本，因此您必须为原始数据库和复制数据库提供足够的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="552dd-237">Because **CompactDatabase** creates a copy of the database, you must have enough disk space for both the original and the duplicate databases.</span></span> <span data-ttu-id="552dd-238">如果没有足够的可用磁盘空间，压缩操作将失败。</span><span class="sxs-lookup"><span data-stu-id="552dd-238">The compact operation fails if there isn't enough disk space available.</span></span> <span data-ttu-id="552dd-239">DstName 复制数据库不必与 SrcName 位于同一个磁盘上。</span><span class="sxs-lookup"><span data-stu-id="552dd-239">The  DstName duplicate database doesn't have to be on the same disk as  SrcName.</span></span> <span data-ttu-id="552dd-240">在成功压缩数据库之后，可以删除 SrcName 文件，并将压缩的 DstName 文件重命名为原始文件名。</span><span class="sxs-lookup"><span data-stu-id="552dd-240">After successfully compacting a database, you can delete the  SrcName file and rename the compacted  DstName file to the original file name.</span></span>

<span data-ttu-id="552dd-241">**CompactDatabase** 方法将所有数据和安全权限设置从由 SrcName 指定的数据库复制到由 DstName 指定的数据库。</span><span class="sxs-lookup"><span data-stu-id="552dd-241">The CompactDatabase method copies all the data and the security permission settings from the database specified by  SrcName to the database specified by  DstName.</span></span>

> [!NOTE]
> <span data-ttu-id="552dd-242">因为**CompactDatabase**方法不能转换 Microsoft Access 对象，所以请不要使用**CompactDatabase**来转换包含此类对象的数据库。</span><span class="sxs-lookup"><span data-stu-id="552dd-242">Because the **CompactDatabase** method doesn't convert Microsoft Access objects, you shouldn't use **CompactDatabase** to convert a database containing such objects.</span></span>

## <a name="encrypted-linked-tables"></a><span data-ttu-id="552dd-243">加密的链接表</span><span class="sxs-lookup"><span data-stu-id="552dd-243">Encrypted linked tables</span></span>

<span data-ttu-id="552dd-244">加密密码取决于正在使用的数据库的文件格式。</span><span class="sxs-lookup"><span data-stu-id="552dd-244">Encrypted passwords are dependent on the file format of the database that you are using.</span></span> <span data-ttu-id="552dd-245">如果使用 Access 2003 (.mdb) 或早期数据库，会有一个密码来保护数据库，另一个单独密码来加密数据库。</span><span class="sxs-lookup"><span data-stu-id="552dd-245">If you are using an Access 2003 (.mdb) or earlier database, you will have one password to protect the database, and a separate password to encrypt the database.</span></span> <span data-ttu-id="552dd-246">对于 Access 2007 (.accdb) 和更高版本 (.mdb) 数据库，唯一选项就是使用同一个密码来加密和保护数据库，因为拥有两个单独密码的选项已删除。</span><span class="sxs-lookup"><span data-stu-id="552dd-246">For Access 2007 (.accdb) and later (.mdb) databases, the only option is to encrypt and protect the database with one password, as the option to have two separate passwords has been removed.</span></span>

> [!NOTE]
> <span data-ttu-id="552dd-247">对于 Access 2007 (.accdb) 数据库，密码就是加密密钥</span><span class="sxs-lookup"><span data-stu-id="552dd-247">For Access 2007 (.accdb) databases, the password is the encryption key</span></span>

<span data-ttu-id="552dd-248">可以使用以下示例 VBA 代码作为命令按钮：</span><span class="sxs-lookup"><span data-stu-id="552dd-248">You can use the following example VBA code for a command button:</span></span>

```vb
    Private Sub Command0_Click()
    
    Dim strSourcePath As String
    Dim strDestPath As String
    
    strSourcePath = "<path>\sourceDb.accdb"
    strDestPath = "<path>\destDb.accdb"
    
    DBEngine.CompactDatabase strSourcePath, strDestPath, dbLangGeneral & ";pwd=Access", dbVersion120, ";pwd=Access"
    
    Set CurrentDatabase = CurrentDb
    Set LinkedTableDef = CurrentDatabase.CreateTableDef 
    ("My Linked Table")
    LinkedTableDef.Connect = "MS Access;pwd=Access";database=" & strDestPath
    LinkedTableDef.RefreshLink
    
    
    MsgBox "Finished"
    
    End Sub 
```

<br/>

<span data-ttu-id="552dd-249">下面的代码示例显示如何借助密码（加密密钥） 使用 CompactDatabase，然后将它链接到该压缩数据库中的一个表。</span><span class="sxs-lookup"><span data-stu-id="552dd-249">The following code sample shows how to use CompactDatabase with a password (encryption key) and then link to a table in that compacted database.</span></span> <span data-ttu-id="552dd-250">请注意必须提供密码。</span><span class="sxs-lookup"><span data-stu-id="552dd-250">Note that a password must be supplied.</span></span>

```vb
    Private Sub CompactAndLink_Click() 
     
    Dim strSourcePath As String
    Dim strDestPath As String
    Dim strSourceTableName As String
    Dim strDestTableName As String
    Dim tdf As TableDef
     
    strSourcePath = "<path>\<database>.accdb"
    strDestPath = "<path>\<database>.accdb"
    strSourceTableName = "<table name in destination database>"
    strDestTableName = "<linked table name>"
     
    ' Compact source database into new destination database with encrypted password
    DBEngine.CompactDatabase strSourcePath, strDestPath, dbLangGeneral & ";pwd=Access", dbVersion120, ";pwd=Access"
     
    ' Link to one of the tables in the destination database
    ' Password must be provided in the Connect property
     
    Set CurrentDatabase = CurrentDb
    Set tdf = CurrentDatabase.CreateTableDef(strDestTableName)
       
        With tdf
            .Connect = ";pwd=Access" & ";DATABASE=" & strDestPath
            .SourceTableName = strSourceTableName
        End With
        
    CurrentDatabase.TableDefs.Append tdf
     
    MsgBox "Database compacted and encrypted password applied. Link to table also completed."
     
    End Sub
```
