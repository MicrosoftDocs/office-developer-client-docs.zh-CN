---
title: Database.NewPassword 方法 (DAO)
TOCTitle: NewPassword Method
ms:assetid: 01c1c454-d651-222c-225a-2b02734a1b7a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844754(v=office.15)
ms:contentKeyID: 48542941
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052943
f1_categories:
- Office.Version=v15
ms.openlocfilehash: f4dca778da3c364d9e9b5a5eaf8ebbc32501853f
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25919358"
---
# <a name="databasenewpassword-method-dao"></a><span data-ttu-id="23515-102">Database.NewPassword 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="23515-102">Database.NewPassword method (DAO)</span></span>


<span data-ttu-id="23515-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="23515-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="23515-104">更改现有 Microsoft Access 数据库引擎数据库的密码（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="23515-104">Changes the password of an existing Microsoft Access database engine database (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="23515-105">语法</span><span class="sxs-lookup"><span data-stu-id="23515-105">Syntax</span></span>

<span data-ttu-id="23515-106">*表达式*。NewPassword （***bstrOld***、 ***bstrNew***）</span><span class="sxs-lookup"><span data-stu-id="23515-106">*expression* .NewPassword(***bstrOld***, ***bstrNew***)</span></span>

<span data-ttu-id="23515-107">*表达式*一个返回**Database**对象的表达式。</span><span class="sxs-lookup"><span data-stu-id="23515-107">*expression* An expression that returns a **Database** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="23515-108">参数</span><span class="sxs-lookup"><span data-stu-id="23515-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="23515-109">名称</span><span class="sxs-lookup"><span data-stu-id="23515-109">Name</span></span></p></th>
<th><p><span data-ttu-id="23515-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="23515-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="23515-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="23515-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="23515-112">说明</span><span class="sxs-lookup"><span data-stu-id="23515-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23515-113">bstrOld</span><span class="sxs-lookup"><span data-stu-id="23515-113">bstrOld</span></span></p></td>
<td><p><span data-ttu-id="23515-114">必需</span><span class="sxs-lookup"><span data-stu-id="23515-114">Required</span></span></p></td>
<td><p><span data-ttu-id="23515-115"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="23515-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="23515-116"><strong>Database</strong> 对象的 <strong>Password</strong> 属性的当前设置。</span><span class="sxs-lookup"><span data-stu-id="23515-116">The current setting of the <strong>Password</strong> property of the <strong>Database</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23515-117">bstrNew</span><span class="sxs-lookup"><span data-stu-id="23515-117">bstrNew</span></span></p></td>
<td><p><span data-ttu-id="23515-118">必需</span><span class="sxs-lookup"><span data-stu-id="23515-118">Required</span></span></p></td>
<td><p><span data-ttu-id="23515-119"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="23515-119"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="23515-120">新的<strong>Database</strong>对象的<strong>Password</strong>属性的设置。</span><span class="sxs-lookup"><span data-stu-id="23515-120">The new setting of the <strong>Password</strong> property of the <strong>Database</strong> object.</span></span></p>

> [!NOTE]
> <span data-ttu-id="23515-p101">[!注释] 使用同时包含大小写字母、数字和符号的强密码。弱密码不混合使用这些元素。例如，强密码：Y6dh!et5。弱密码：House27。请使用可以记住的强密码，这样就不必记录密码了。</span><span class="sxs-lookup"><span data-stu-id="23515-p101">Use strong passwords that combine upper- and lowercase letters, numbers, and symbols. Weak passwords don't mix these elements. Strong password: Y6dh!et5. Weak password: House27. Use a strong password that you can remember so that you don't have to write it down.</span></span>


</td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="23515-126">说明</span><span class="sxs-lookup"><span data-stu-id="23515-126">Remarks</span></span>

<span data-ttu-id="23515-127">BstrOld 和 bstrNew 字符串长度最多为 20 个字符，并且可以包括除 ASCII 字符 0 (null) 的任何字符。</span><span class="sxs-lookup"><span data-stu-id="23515-127">The bstrOld and bstrNew strings can be up to 20 characters long and can include any characters except the ASCII character 0 (null).</span></span> <span data-ttu-id="23515-128">若要清除密码，请使用零长度字符串 ("") 的 bstrNew。</span><span class="sxs-lookup"><span data-stu-id="23515-128">To clear the password, use a zero-length string ("") for bstrNew.</span></span>

<span data-ttu-id="23515-129">密码区分大小写。</span><span class="sxs-lookup"><span data-stu-id="23515-129">Passwords are case-sensitive.</span></span>

<span data-ttu-id="23515-130">如果数据库没有密码，Microsoft Access 数据库引擎将通过传递旧密码的零长度字符串 ("") 自动创建一个密码。</span><span class="sxs-lookup"><span data-stu-id="23515-130">If a database has no password, the Microsoft Access database engine will automatically create one by passing a zero-length string ("") for the old password.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="23515-131">[!重要信息] 如果丢失了密码，则永远不能再次打开数据库。</span><span class="sxs-lookup"><span data-stu-id="23515-131">If you lose your password, you can never open the database again.</span></span>


