---
title: DBEngine.CreateDatabase Method (DAO)
TOCTitle: CreateDatabase Method
ms:assetid: d5821a4b-483a-b8fa-e929-5f036057d8c4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835033(v=office.15)
ms:contentKeyID: 48547966
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052972
f1_categories:
- Office.Version=v15
ms.openlocfilehash: f1f47e403b1b1c61bb766d28be05558f28dba8f1
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466537"
---
# <a name="dbenginecreatedatabase-method-dao"></a><span data-ttu-id="c733b-102">DBEngine.CreateDatabase Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="c733b-102">DBEngine.CreateDatabase Method (DAO)</span></span>


<span data-ttu-id="c733b-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c733b-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c733b-p101">创建一个新的 **[Database](database-object-dao.md)** 对象，将数据库保存到磁盘，然后返回一个打开的 **Database** 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="c733b-p101">Creates a new **[Database](database-object-dao.md)** object, saves the database to disk, and returns an opened **Database** object (Microsoft Access workspaces only). .</span></span>

## <a name="syntax"></a><span data-ttu-id="c733b-106">语法</span><span class="sxs-lookup"><span data-stu-id="c733b-106">Syntax</span></span>

<span data-ttu-id="c733b-107">*表达式*。CreateDatabase （***名称***、***区域设置***，***选项***）</span><span class="sxs-lookup"><span data-stu-id="c733b-107">*expression* .CreateDatabase(***Name***, ***Locale***, ***Option***)</span></span>

<span data-ttu-id="c733b-108">*表达式*一个代表**DBEngine**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="c733b-108">*expression* A variable that represents a **DBEngine** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="c733b-109">参数</span><span class="sxs-lookup"><span data-stu-id="c733b-109">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c733b-110">名称</span><span class="sxs-lookup"><span data-stu-id="c733b-110">Name</span></span></p></th>
<th><p><span data-ttu-id="c733b-111">必需/可选</span><span class="sxs-lookup"><span data-stu-id="c733b-111">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="c733b-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="c733b-112">Data Type</span></span></p></th>
<th><p><span data-ttu-id="c733b-113">说明</span><span class="sxs-lookup"><span data-stu-id="c733b-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c733b-114">名称</span><span class="sxs-lookup"><span data-stu-id="c733b-114">Name</span></span></p></td>
<td><p><span data-ttu-id="c733b-115">必需</span><span class="sxs-lookup"><span data-stu-id="c733b-115">Required</span></span></p></td>
<td><p><span data-ttu-id="c733b-116"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-116"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-117">一个最长 255 个字符的字符串，是正在创建的数据库文件的名称。</span><span class="sxs-lookup"><span data-stu-id="c733b-117">A String up to 255 characters long that is the name of the database file that you're creating.</span></span> <span data-ttu-id="c733b-118">它可以是完整路径和文件名称。</span><span class="sxs-lookup"><span data-stu-id="c733b-118">It can be the full path and file name.</span></span> <span data-ttu-id="c733b-119">如果您的网络支持，您还可以指定一个网络路径，如&quot; \\server1\share1\dir1\db1&quot;。</span><span class="sxs-lookup"><span data-stu-id="c733b-119">If your network supports it, you can also specify a network path, such as &quot;\\server1\share1\dir1\db1&quot;.</span></span> <span data-ttu-id="c733b-120">仅可以使用此方法来创建 Microsoft Access 数据库文件。</span><span class="sxs-lookup"><span data-stu-id="c733b-120">You can only create Microsoft Access database files with this method.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c733b-121">Locale</span><span class="sxs-lookup"><span data-stu-id="c733b-121">Locale</span></span></p></td>
<td><p><span data-ttu-id="c733b-122">必需</span><span class="sxs-lookup"><span data-stu-id="c733b-122">Required</span></span></p></td>
<td><p><span data-ttu-id="c733b-123"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-123"><strong>String</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c733b-p103">一个字符串表达式，根据“设置”中的定义指定创建数据库时使用的整理顺序。必须提供此参数，否则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="c733b-p103">A string expression that specifies a collating order for creating the database, as specified in Settings. You must supply this argument or an error occurs.</span></span></p></li>
<li><p><span data-ttu-id="c733b-126">您还可以通过将密码字符串创建新的<strong>Database</strong>对象的密码 (开头&quot;; pwd =&quot; ) 与<em>locale</em>参数，如下所示中的一个常量：</span><span class="sxs-lookup"><span data-stu-id="c733b-126">You can also create a password for the new <strong>Database</strong> object by concatenating the password string (starting with &quot;;pwd=&quot; ) with a constant in the <em>locale</em> argument, like this:</span></span></p></li>
<li><p><span data-ttu-id="c733b-127">dbLangSpanish &amp; &quot;; pwd = NewPassword&quot;</span><span class="sxs-lookup"><span data-stu-id="c733b-127">dbLangSpanish &amp; &quot;;pwd=NewPassword&quot;</span></span></p></li>
<li><p><span data-ttu-id="c733b-128">如果需要使用默认的 <em>locale</em>，但又要指定密码，只需要为 <em>locale</em> 参数输入密码字符串：</span><span class="sxs-lookup"><span data-stu-id="c733b-128">If you want to use the default <em>locale</em>, but specify a password, simply enter a password string for the <em>locale</em> argument:</span></span></p></li>
<li><p><span data-ttu-id="c733b-129">&quot;pwd = NewPassword&quot;</span><span class="sxs-lookup"><span data-stu-id="c733b-129">&quot;;pwd=NewPassword&quot;</span></span></p></li>
<li><p><span data-ttu-id="c733b-p104">[!注释] 使用同时包含大小写字母、数字和符号的强密码。弱密码不混合使用这些元素。例如，强密码：Y6dh!et5。弱密码：House27。请使用可以记住的强密码，这样就不必记录密码了。</span><span class="sxs-lookup"><span data-stu-id="c733b-p104">Use strong passwords that combine upper- and lowercase letters, numbers, and symbols. Weak passwords don't mix these elements. Strong password: Y6dh!et5. Weak password: House27. Use a strong password that you can remember so that you don't have to write it down.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c733b-135">选项</span><span class="sxs-lookup"><span data-stu-id="c733b-135">Option</span></span></p></td>
<td><p><span data-ttu-id="c733b-136">可选</span><span class="sxs-lookup"><span data-stu-id="c733b-136">Optional</span></span></p></td>
<td><p><span data-ttu-id="c733b-137"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-137"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-p105">一个常量或常量组合，根据“设置”中的指定指示一个或多个选项。可通过对相应的常量求和来组合选项。</span><span class="sxs-lookup"><span data-stu-id="c733b-p105">A constant or combination of constants that indicates one or more options, as specified in Settings. You can combine options by summing the corresponding constants.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="c733b-140">注解</span><span class="sxs-lookup"><span data-stu-id="c733b-140">Remarks</span></span>

<span data-ttu-id="c733b-141">可以使用 locale 参数的下列常量之一，指定用于字符串比较的文本的 **[CollatingOrder](database-collatingorder-property-dao.md)** 属性。</span><span class="sxs-lookup"><span data-stu-id="c733b-141">You can use one of the following constants for the locale argument to specify the **[CollatingOrder](database-collatingorder-property-dao.md)** property of text for string comparisons.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c733b-142">常量</span><span class="sxs-lookup"><span data-stu-id="c733b-142">Constant</span></span></p></th>
<th><p><span data-ttu-id="c733b-143">整理顺序</span><span class="sxs-lookup"><span data-stu-id="c733b-143">Collating order</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c733b-144"><strong>dbLangGeneral</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-144"><strong>dbLangGeneral</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-145">英语、德语、法语、葡萄牙语、意大利语和现代西班牙语</span><span class="sxs-lookup"><span data-stu-id="c733b-145">English, German, French, Portuguese, Italian, and Modern Spanish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c733b-146"><strong>dbLangArabic</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-146"><strong>dbLangArabic</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-147">阿拉伯语</span><span class="sxs-lookup"><span data-stu-id="c733b-147">Arabic</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c733b-148"><strong>dbLangChineseSimplified</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-148"><strong>dbLangChineseSimplified</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-149">简体中文</span><span class="sxs-lookup"><span data-stu-id="c733b-149">Simplified Chinese</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c733b-150"><strong>dbLangChineseTraditional</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-150"><strong>dbLangChineseTraditional</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-151">繁体中文</span><span class="sxs-lookup"><span data-stu-id="c733b-151">Traditional Chinese</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c733b-152"><strong>dbLangCyrillic</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-152"><strong>dbLangCyrillic</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-153">俄语</span><span class="sxs-lookup"><span data-stu-id="c733b-153">Russian</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c733b-154"><strong>dbLangCzech</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-154"><strong>dbLangCzech</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-155">捷克语</span><span class="sxs-lookup"><span data-stu-id="c733b-155">Czech</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c733b-156"><strong>dbLangDutch</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-156"><strong>dbLangDutch</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-157">荷兰语</span><span class="sxs-lookup"><span data-stu-id="c733b-157">Dutch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c733b-158"><strong>dbLangGreek</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-158"><strong>dbLangGreek</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-159">希腊语</span><span class="sxs-lookup"><span data-stu-id="c733b-159">Greek</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c733b-160"><strong>dbLangHebrew</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-160"><strong>dbLangHebrew</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-161">希伯来语</span><span class="sxs-lookup"><span data-stu-id="c733b-161">Hebrew</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c733b-162"><strong>dbLangHungarian</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-162"><strong>dbLangHungarian</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-163">匈牙利语</span><span class="sxs-lookup"><span data-stu-id="c733b-163">Hungarian</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c733b-164"><strong>dbLangIcelandic</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-164"><strong>dbLangIcelandic</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-165">冰岛语</span><span class="sxs-lookup"><span data-stu-id="c733b-165">Icelandic</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c733b-166"><strong>dbLangJapanese</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-166"><strong>dbLangJapanese</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-167">日语</span><span class="sxs-lookup"><span data-stu-id="c733b-167">Japanese</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c733b-168"><strong>dbLangKorean</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-168"><strong>dbLangKorean</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-169">朝鲜语</span><span class="sxs-lookup"><span data-stu-id="c733b-169">Korean</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c733b-170"><strong>dbLangNordic</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-170"><strong>dbLangNordic</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-171">北欧语言（仅适用于 Microsoft Jet 数据库引擎 1.0 版）</span><span class="sxs-lookup"><span data-stu-id="c733b-171">Nordic languages (Microsoft Jet database engine version 1.0 only)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c733b-172"><strong>dbLangNorwDan</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-172"><strong>dbLangNorwDan</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-173">挪威语和丹麦语</span><span class="sxs-lookup"><span data-stu-id="c733b-173">Norwegian and Danish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c733b-174"><strong>dbLangPolish</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-174"><strong>dbLangPolish</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-175">波兰语</span><span class="sxs-lookup"><span data-stu-id="c733b-175">Polish</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c733b-176"><strong>dbLangSlovenian</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-176"><strong>dbLangSlovenian</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-177">斯洛文尼亚语</span><span class="sxs-lookup"><span data-stu-id="c733b-177">Slovenian</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c733b-178"><strong>dbLangSpanish</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-178"><strong>dbLangSpanish</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-179">传统西班牙语</span><span class="sxs-lookup"><span data-stu-id="c733b-179">Traditional Spanish</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c733b-180"><strong>dbLangSwedFin</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-180"><strong>dbLangSwedFin</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-181">瑞典语和芬兰语</span><span class="sxs-lookup"><span data-stu-id="c733b-181">Swedish and Finnish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c733b-182"><strong>dbLangThai</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-182"><strong>dbLangThai</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-183">泰语</span><span class="sxs-lookup"><span data-stu-id="c733b-183">Thai</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c733b-184"><strong>dbLangTurkish</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-184"><strong>dbLangTurkish</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-185">土耳其语</span><span class="sxs-lookup"><span data-stu-id="c733b-185">Turkish</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c733b-186">可以在 options 参数中使用下列一个或多个常量，以指定数据格式应使用的版本，以及是否对数据库加密。</span><span class="sxs-lookup"><span data-stu-id="c733b-186">You can use one or more of the following constants in the options argument to specify which version the data format should have and whether or not to encrypt the database.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c733b-187">常量</span><span class="sxs-lookup"><span data-stu-id="c733b-187">Constant</span></span></p></th>
<th><p><span data-ttu-id="c733b-188">说明</span><span class="sxs-lookup"><span data-stu-id="c733b-188">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c733b-189"><strong>dbEncrypt</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-189"><strong>dbEncrypt</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-190">创建加密的数据库。</span><span class="sxs-lookup"><span data-stu-id="c733b-190">Creates an encrypted database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c733b-191"><strong>dbVersion10</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-191"><strong>dbVersion10</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-192">创建一个使用 Microsoft Jet 数据库引擎 1.0 版文件格式的数据库。</span><span class="sxs-lookup"><span data-stu-id="c733b-192">Creates a database that uses the Microsoft Jet database engine version 1.0 file format.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c733b-193"><strong>dbVersion11</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-193"><strong>dbVersion11</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-194">创建一个使用 Microsoft Jet 数据库引擎 1.1 版文件格式的数据库。</span><span class="sxs-lookup"><span data-stu-id="c733b-194">Creates a database that uses the Microsoft Jet database engine version 1.1 file format.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c733b-195"><strong>dbVersion20</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-195"><strong>dbVersion20</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-196">创建一个使用 Microsoft Jet 数据库引擎 2.0 版文件格式的数据库。</span><span class="sxs-lookup"><span data-stu-id="c733b-196">Creates a database that uses the Microsoft Jet database engine version 2.0 file format.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c733b-197"><strong>dbVersion30</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-197"><strong>dbVersion30</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-198">创建一个使用 Microsoft Jet 数据库引擎 3.0 版文件格式的数据库（与 3.5 版兼容）。</span><span class="sxs-lookup"><span data-stu-id="c733b-198">Creates a database that uses the Microsoft Jet database engine version 3.0 file format (compatible with version 3.5).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c733b-199"><strong>dbVersion40</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-199"><strong>dbVersion40</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-200">创建一个使用 Microsoft Jet 数据库引擎 4.0 版文件格式的数据库。</span><span class="sxs-lookup"><span data-stu-id="c733b-200">Creates a database that uses the Microsoft Jet database engine version 4.0 file format.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c733b-201"><strong>dbVersion120</strong></span><span class="sxs-lookup"><span data-stu-id="c733b-201"><strong>dbVersion120</strong></span></span></p></td>
<td><p><span data-ttu-id="c733b-202">创建一个使用 Microsoft Access 数据库引擎 12.0 版文件格式的数据库。</span><span class="sxs-lookup"><span data-stu-id="c733b-202">Creates a database that uses the Microsoft Access database engine version 12.0 file format.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c733b-203">如果省略加密常量， **CreateDatabase** 将创建一个不加密的数据库。</span><span class="sxs-lookup"><span data-stu-id="c733b-203">If you omit the encryption constant, **CreateDatabase** creates an un-encrypted database.</span></span>

<span data-ttu-id="c733b-p106">可使用 **CreateDatabase** 方法创建和打开一个新的空数据库，然后返回 **Database** 对象。必须通过使用其他 DAO 对象完成该数据库的结构和内容。如果要对现有的数据库制作一个部分副本或完整副本，可以使用 **[CompactDatabase](dbengine-compactdatabase-method-dao.md)** 方法制作一个能够自定义的副本。</span><span class="sxs-lookup"><span data-stu-id="c733b-p106">Use the **CreateDatabase** method to create and open a new, empty database, and return the **Database** object. You must complete its structure and content by using additional DAO objects. If you want to make a partial or complete copy of an existing database, you can use the **[CompactDatabase](dbengine-compactdatabase-method-dao.md)** method to make a copy that you can customize.</span></span>
