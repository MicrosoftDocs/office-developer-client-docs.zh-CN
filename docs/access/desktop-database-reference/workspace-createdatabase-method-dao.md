---
title: Workspace.CreateDatabase Method (DAO)
TOCTitle: CreateDatabase Method
ms:assetid: c0ad986e-3b4d-f781-f782-5aa3cdccea7d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822832(v=office.15)
ms:contentKeyID: 48547514
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8f246ce2cb29ce3933d8102ce51733652709579e
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465705"
---
# <a name="workspacecreatedatabase-method-dao"></a><span data-ttu-id="00c6a-102">Workspace.CreateDatabase Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="00c6a-102">Workspace.CreateDatabase Method (DAO)</span></span>


<span data-ttu-id="00c6a-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="00c6a-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="00c6a-104">创建一个新的 **[Database](database-object-dao.md)** 对象，将数据库保存到磁盘，然后返回一个打开的 **Database** 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="00c6a-104">Creates a new **[Database](database-object-dao.md)** object, saves the database to disk, and returns an opened **Database** object (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="00c6a-105">语法</span><span class="sxs-lookup"><span data-stu-id="00c6a-105">Syntax</span></span>

<span data-ttu-id="00c6a-106">*表达式*。CreateDatabase （***名称***、***连接***，***选项***）</span><span class="sxs-lookup"><span data-stu-id="00c6a-106">*expression* .CreateDatabase(***Name***, ***Connect***, ***Option***)</span></span>

<span data-ttu-id="00c6a-107">*表达式*一个代表**Workspace**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="00c6a-107">*expression* A variable that represents a **Workspace** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="00c6a-108">参数</span><span class="sxs-lookup"><span data-stu-id="00c6a-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="00c6a-109">名称</span><span class="sxs-lookup"><span data-stu-id="00c6a-109">Name</span></span></p></th>
<th><p><span data-ttu-id="00c6a-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="00c6a-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="00c6a-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="00c6a-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="00c6a-112">说明</span><span class="sxs-lookup"><span data-stu-id="00c6a-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00c6a-113">名称</span><span class="sxs-lookup"><span data-stu-id="00c6a-113">Name</span></span></p></td>
<td><p><span data-ttu-id="00c6a-114">必需</span><span class="sxs-lookup"><span data-stu-id="00c6a-114">Required</span></span></p></td>
<td><p><span data-ttu-id="00c6a-115"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-116">一个最长 255 个字符的字符串，是正在创建的数据库文件的名称。</span><span class="sxs-lookup"><span data-stu-id="00c6a-116">A String up to 255 characters long that is the name of the database file that you're creating.</span></span> <span data-ttu-id="00c6a-117">它可以是完整路径和文件名称。</span><span class="sxs-lookup"><span data-stu-id="00c6a-117">It can be the full path and file name.</span></span> <span data-ttu-id="00c6a-118">如果您的网络支持，您还可以指定一个网络路径，如&quot; \\server1\share1\dir1\db1&quot;。</span><span class="sxs-lookup"><span data-stu-id="00c6a-118">If your network supports it, you can also specify a network path, such as &quot;\\server1\share1\dir1\db1&quot;.</span></span> <span data-ttu-id="00c6a-119">仅可以使用此方法来创建 Microsoft Access 数据库文件。</span><span class="sxs-lookup"><span data-stu-id="00c6a-119">You can only create Microsoft Access database files with this method.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c6a-120">在浏览器中</span><span class="sxs-lookup"><span data-stu-id="00c6a-120">Connect</span></span></p></td>
<td><p><span data-ttu-id="00c6a-121">必需</span><span class="sxs-lookup"><span data-stu-id="00c6a-121">Required</span></span></p></td>
<td><p><span data-ttu-id="00c6a-122"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-122"><strong>String</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="00c6a-p102">一个字符串表达式，根据“设置”中的定义指定创建数据库时使用的整理顺序。必须提供此参数，否则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="00c6a-p102">A string expression that specifies a collating order for creating the database, as specified in Settings. You must supply this argument or an error occurs.</span></span></p></li>
<li><p><span data-ttu-id="00c6a-125">您还可以通过将密码字符串创建新的<strong>Database</strong>对象的密码 (开头&quot;; pwd =&quot;) 与<em>locale</em>参数，如下所示中的一个常量：</span><span class="sxs-lookup"><span data-stu-id="00c6a-125">You can also create a password for the new <strong>Database</strong> object by concatenating the password string (starting with &quot;;pwd=&quot;) with a constant in the <em>locale</em> argument, like this:</span></span></p></li>
<li><p><span data-ttu-id="00c6a-126">dbLangSpanish &amp; &quot;; pwd = NewPassword&quot;</span><span class="sxs-lookup"><span data-stu-id="00c6a-126">dbLangSpanish &amp; &quot;;pwd=NewPassword&quot;</span></span></p></li>
<li><p><span data-ttu-id="00c6a-127">如果需要使用默认的 <em>locale</em>，但又要指定密码，只需要为 <em>locale</em> 参数输入密码字符串：</span><span class="sxs-lookup"><span data-stu-id="00c6a-127">If you want to use the default <em>locale</em>, but specify a password, simply enter a password string for the <em>locale</em> argument:</span></span></p></li>
<li><p><span data-ttu-id="00c6a-128">&quot;pwd = NewPassword&quot;</span><span class="sxs-lookup"><span data-stu-id="00c6a-128">&quot;;pwd=NewPassword&quot;</span></span></p></li>
<li><p><span data-ttu-id="00c6a-p103">[!注释] 使用同时包含大小写字母、数字和符号的强密码。弱密码不混合使用这些元素。例如，强密码：Y6dh!et5。弱密码：House27。请使用可以记住的强密码，这样就不必记录密码了。</span><span class="sxs-lookup"><span data-stu-id="00c6a-p103">Use strong passwords that combine upper- and lowercase letters, numbers, and symbols. Weak passwords don't mix these elements. Strong password: Y6dh!et5. Weak password: House27. Use a strong password that you can remember so that you don't have to write it down.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c6a-134">选项</span><span class="sxs-lookup"><span data-stu-id="00c6a-134">Option</span></span></p></td>
<td><p><span data-ttu-id="00c6a-135">可选</span><span class="sxs-lookup"><span data-stu-id="00c6a-135">Optional</span></span></p></td>
<td><p><span data-ttu-id="00c6a-136"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-136"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-p104">一个常量或常量组合，根据“设置”中的指定指示一个或多个选项。可通过对相应的常量求和来组合选项。</span><span class="sxs-lookup"><span data-stu-id="00c6a-p104">A constant or combination of constants that indicates one or more options, as specified in Settings. You can combine options by summing the corresponding constants.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="00c6a-139">注解</span><span class="sxs-lookup"><span data-stu-id="00c6a-139">Remarks</span></span>

<span data-ttu-id="00c6a-140">可以使用 locale 参数的下列常量之一，指定用于字符串比较的文本的 [CollatingOrder](database-collatingorder-property-dao.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="00c6a-140">You can use one of the following constants for the locale argument to specify the [CollatingOrder](database-collatingorder-property-dao.md) property of text for string comparisons.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="00c6a-141">常量</span><span class="sxs-lookup"><span data-stu-id="00c6a-141">Constant</span></span></p></th>
<th><p><span data-ttu-id="00c6a-142">整理顺序</span><span class="sxs-lookup"><span data-stu-id="00c6a-142">Collating order</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00c6a-143"><strong>dbLangGeneral</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-143"><strong>dbLangGeneral</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-144">英语、德语、法语、葡萄牙语、意大利语和现代西班牙语</span><span class="sxs-lookup"><span data-stu-id="00c6a-144">English, German, French, Portuguese, Italian, and Modern Spanish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c6a-145"><strong>dbLangArabic</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-145"><strong>dbLangArabic</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-146">阿拉伯语</span><span class="sxs-lookup"><span data-stu-id="00c6a-146">Arabic</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c6a-147"><strong>dbLangChineseSimplified</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-147"><strong>dbLangChineseSimplified</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-148">简体中文</span><span class="sxs-lookup"><span data-stu-id="00c6a-148">Simplified Chinese</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c6a-149"><strong>dbLangChineseTraditional</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-149"><strong>dbLangChineseTraditional</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-150">繁体中文</span><span class="sxs-lookup"><span data-stu-id="00c6a-150">Traditional Chinese</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c6a-151"><strong>dbLangCyrillic</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-151"><strong>dbLangCyrillic</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-152">俄语</span><span class="sxs-lookup"><span data-stu-id="00c6a-152">Russian</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c6a-153"><strong>dbLangCzech</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-153"><strong>dbLangCzech</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-154">捷克语</span><span class="sxs-lookup"><span data-stu-id="00c6a-154">Czech</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c6a-155"><strong>dbLangDutch</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-155"><strong>dbLangDutch</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-156">荷兰语</span><span class="sxs-lookup"><span data-stu-id="00c6a-156">Dutch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c6a-157"><strong>dbLangGreek</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-157"><strong>dbLangGreek</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-158">希腊语</span><span class="sxs-lookup"><span data-stu-id="00c6a-158">Greek</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c6a-159"><strong>dbLangHebrew</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-159"><strong>dbLangHebrew</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-160">希伯来语</span><span class="sxs-lookup"><span data-stu-id="00c6a-160">Hebrew</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c6a-161"><strong>dbLangHungarian</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-161"><strong>dbLangHungarian</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-162">匈牙利语</span><span class="sxs-lookup"><span data-stu-id="00c6a-162">Hungarian</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c6a-163"><strong>dbLangIcelandic</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-163"><strong>dbLangIcelandic</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-164">冰岛语</span><span class="sxs-lookup"><span data-stu-id="00c6a-164">Icelandic</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c6a-165"><strong>dbLangJapanese</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-165"><strong>dbLangJapanese</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-166">日语</span><span class="sxs-lookup"><span data-stu-id="00c6a-166">Japanese</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c6a-167"><strong>dbLangKorean</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-167"><strong>dbLangKorean</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-168">朝鲜语</span><span class="sxs-lookup"><span data-stu-id="00c6a-168">Korean</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c6a-169"><strong>dbLangNordic</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-169"><strong>dbLangNordic</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-170">北欧语言（仅适用于 Microsoft Jet 数据库引擎 1.0 版）</span><span class="sxs-lookup"><span data-stu-id="00c6a-170">Nordic languages (Microsoft Jet database engine version 1.0 only)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c6a-171"><strong>dbLangNorwDan</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-171"><strong>dbLangNorwDan</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-172">挪威语和丹麦语</span><span class="sxs-lookup"><span data-stu-id="00c6a-172">Norwegian and Danish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c6a-173"><strong>dbLangPolish</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-173"><strong>dbLangPolish</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-174">波兰语</span><span class="sxs-lookup"><span data-stu-id="00c6a-174">Polish</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c6a-175"><strong>dbLangSlovenian</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-175"><strong>dbLangSlovenian</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-176">斯洛文尼亚语</span><span class="sxs-lookup"><span data-stu-id="00c6a-176">Slovenian</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c6a-177"><strong>dbLangSpanish</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-177"><strong>dbLangSpanish</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-178">传统西班牙语</span><span class="sxs-lookup"><span data-stu-id="00c6a-178">Traditional Spanish</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c6a-179"><strong>dbLangSwedFin</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-179"><strong>dbLangSwedFin</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-180">瑞典语和芬兰语</span><span class="sxs-lookup"><span data-stu-id="00c6a-180">Swedish and Finnish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c6a-181"><strong>dbLangThai</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-181"><strong>dbLangThai</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-182">泰语</span><span class="sxs-lookup"><span data-stu-id="00c6a-182">Thai</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c6a-183"><strong>dbLangTurkish</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-183"><strong>dbLangTurkish</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-184">土耳其语</span><span class="sxs-lookup"><span data-stu-id="00c6a-184">Turkish</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="00c6a-185">可以在 options 参数中使用下列一个或多个常量，以指定数据格式应使用的版本，以及是否对数据库加密。</span><span class="sxs-lookup"><span data-stu-id="00c6a-185">You can use one or more of the following constants in the options argument to specify which version the data format should have and whether or not to encrypt the database.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="00c6a-186">常量</span><span class="sxs-lookup"><span data-stu-id="00c6a-186">Constant</span></span></p></th>
<th><p><span data-ttu-id="00c6a-187">说明</span><span class="sxs-lookup"><span data-stu-id="00c6a-187">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00c6a-188"><strong>dbEncrypt</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-188"><strong>dbEncrypt</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-189">创建加密的数据库。</span><span class="sxs-lookup"><span data-stu-id="00c6a-189">Creates an encrypted database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c6a-190"><strong>dbVersion10</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-190"><strong>dbVersion10</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-191">创建一个使用 Microsoft Jet 数据库引擎 1.0 版文件格式的数据库。</span><span class="sxs-lookup"><span data-stu-id="00c6a-191">Creates a database that uses the Microsoft Jet database engine version 1.0 file format.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c6a-192"><strong>dbVersion11</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-192"><strong>dbVersion11</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-193">创建一个使用 Microsoft Jet 数据库引擎 1.1 版文件格式的数据库。</span><span class="sxs-lookup"><span data-stu-id="00c6a-193">Creates a database that uses the Microsoft Jet database engine version 1.1 file format.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c6a-194"><strong>dbVersion20</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-194"><strong>dbVersion20</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-195">创建一个使用 Microsoft Jet 数据库引擎 2.0 版文件格式的数据库。</span><span class="sxs-lookup"><span data-stu-id="00c6a-195">Creates a database that uses the Microsoft Jet database engine version 2.0 file format.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c6a-196"><strong>dbVersion30</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-196"><strong>dbVersion30</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-197">创建一个使用 Microsoft Jet 数据库引擎 3.0 版文件格式的数据库（与 3.5 版兼容）。</span><span class="sxs-lookup"><span data-stu-id="00c6a-197">Creates a database that uses the Microsoft Jet database engine version 3.0 file format (compatible with version 3.5).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00c6a-198"><strong>dbVersion40</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-198"><strong>dbVersion40</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-199">创建一个使用 Microsoft Jet 数据库引擎 4.0 版文件格式的数据库。</span><span class="sxs-lookup"><span data-stu-id="00c6a-199">Creates a database that uses the Microsoft Jet database engine version 4.0 file format.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00c6a-200"><strong>dbVersion120</strong></span><span class="sxs-lookup"><span data-stu-id="00c6a-200"><strong>dbVersion120</strong></span></span></p></td>
<td><p><span data-ttu-id="00c6a-201">创建一个使用 Microsoft Access 数据库引擎 12.0 版文件格式的数据库。</span><span class="sxs-lookup"><span data-stu-id="00c6a-201">Creates a database that uses the Microsoft Access database engine version 12.0 file format.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="00c6a-202">如果省略加密常量， **CreateDatabase** 将创建一个不加密的数据库。</span><span class="sxs-lookup"><span data-stu-id="00c6a-202">If you omit the encryption constant, **CreateDatabase** creates an un-encrypted database.</span></span>

<span data-ttu-id="00c6a-p105">可使用 **CreateDatabase** 方法创建和打开一个新的空数据库，然后返回 **Database** 对象。必须通过使用其他 DAO 对象完成该数据库的结构和内容。如果要对现有的数据库制作一个部分副本或完整副本，可以使用 **[CompactDatabase](dbengine-compactdatabase-method-dao.md)** 方法制作一个能够自定义的副本。</span><span class="sxs-lookup"><span data-stu-id="00c6a-p105">Use the **CreateDatabase** method to create and open a new, empty database, and return the **Database** object. You must complete its structure and content by using additional DAO objects. If you want to make a partial or complete copy of an existing database, you can use the **[CompactDatabase](dbengine-compactdatabase-method-dao.md)** method to make a copy that you can customize.</span></span>

## <a name="example"></a><span data-ttu-id="00c6a-206">示例</span><span class="sxs-lookup"><span data-stu-id="00c6a-206">Example</span></span>

<span data-ttu-id="00c6a-207">以下示例使用 **CreateDatabase** 创建一个新的加密 **Database** 对象。</span><span class="sxs-lookup"><span data-stu-id="00c6a-207">This example uses **CreateDatabase** to create a new, encrypted **Database** object.</span></span>

```vb
    Sub CreateDatabaseX() 
     
       Dim wrkDefault As Workspace 
       Dim dbsNew As DATABASE 
       Dim prpLoop As Property 
     
       ' Get default Workspace. 
       Set wrkDefault = DBEngine.Workspaces(0) 
     
       ' Make sure there isn't already a file with the name of  
       ' the new database. 
       If Dir("NewDB.mdb") <> "" Then Kill "NewDB.mdb" 
     
       ' Create a new encrypted database with the specified  
       ' collating order. 
       Set dbsNew = wrkDefault.CreateDatabase("NewDB.mdb", _ 
          dbLangGeneral, dbEncrypt) 
     
       With dbsNew 
          Debug.Print "Properties of " & .Name 
          ' Enumerate the Properties collection of the new  
          ' Database object. 
          For Each prpLoop In .Properties 
             If prpLoop <> "" Then Debug.Print "  " & _ 
                prpLoop.Name & " = " & prpLoop 
          Next prpLoop 
       End With 
     
       dbsNew.Close 
     
    End Sub
```