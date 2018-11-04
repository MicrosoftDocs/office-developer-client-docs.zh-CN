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
ms.openlocfilehash: 567a8901b06bf73a57addc8907e2eb5517e5c2e4
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949514"
---
# <a name="databasenewpassword-method-dao"></a><span data-ttu-id="bb06a-102">Database.NewPassword 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="bb06a-102">Database.NewPassword method (DAO)</span></span>

<span data-ttu-id="bb06a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="bb06a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bb06a-104">更改现有 Microsoft Access 数据库引擎数据库的密码（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="bb06a-104">Changes the password of an existing Microsoft Access database engine database (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="bb06a-105">语法</span><span class="sxs-lookup"><span data-stu-id="bb06a-105">Syntax</span></span>

<span data-ttu-id="bb06a-106">*表达式*。NewPassword （***bstrOld***、 ***bstrNew***）</span><span class="sxs-lookup"><span data-stu-id="bb06a-106">*expression* .NewPassword(***bstrOld***, ***bstrNew***)</span></span>

<span data-ttu-id="bb06a-107">*表达式*一个返回**Database**对象的表达式。</span><span class="sxs-lookup"><span data-stu-id="bb06a-107">*expression* An expression that returns a **Database** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="bb06a-108">参数</span><span class="sxs-lookup"><span data-stu-id="bb06a-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bb06a-109">名称</span><span class="sxs-lookup"><span data-stu-id="bb06a-109">Name</span></span></p></th>
<th><p><span data-ttu-id="bb06a-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="bb06a-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="bb06a-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="bb06a-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="bb06a-112">说明</span><span class="sxs-lookup"><span data-stu-id="bb06a-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb06a-113"><em>bstrOld</em></span><span class="sxs-lookup"><span data-stu-id="bb06a-113"><em>bstrOld</em></span></span></p></td>
<td><p><span data-ttu-id="bb06a-114">必需</span><span class="sxs-lookup"><span data-stu-id="bb06a-114">Required</span></span></p></td>
<td><p><span data-ttu-id="bb06a-115"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="bb06a-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="bb06a-116"><strong>Database</strong> 对象的 <strong>Password</strong> 属性的当前设置。</span><span class="sxs-lookup"><span data-stu-id="bb06a-116">The current setting of the <strong>Password</strong> property of the <strong>Database</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb06a-117"><em>bstrNew</em></span><span class="sxs-lookup"><span data-stu-id="bb06a-117"><em>bstrNew</em></span></span></p></td>
<td><p><span data-ttu-id="bb06a-118">必需</span><span class="sxs-lookup"><span data-stu-id="bb06a-118">Required</span></span></p></td>
<td><p><span data-ttu-id="bb06a-119"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="bb06a-119"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="bb06a-120">新的<strong>Database</strong>对象的<strong>Password</strong>属性的设置。</span><span class="sxs-lookup"><span data-stu-id="bb06a-120">The new setting of the <strong>Password</strong> property of the <strong>Database</strong> object.</span></span></p>
<p><span data-ttu-id="bb06a-121"><strong>注意</strong>： 使用合并和小写字母、 数字和符号的强密码。</span><span class="sxs-lookup"><span data-stu-id="bb06a-121"><strong>NOTE</strong>: Use strong passwords that combine upper- and lowercase letters, numbers, and symbols.</span></span> <span data-ttu-id="bb06a-122">弱密码不混合使用这些元素。</span><span class="sxs-lookup"><span data-stu-id="bb06a-122">Weak passwords don't mix these elements.</span></span> <span data-ttu-id="bb06a-123">例如，强密码：Y6dh!et5。</span><span class="sxs-lookup"><span data-stu-id="bb06a-123">Strong password: Y6dh!et5.</span></span> <span data-ttu-id="bb06a-124">弱密码：House27。</span><span class="sxs-lookup"><span data-stu-id="bb06a-124">Weak password: House27.</span></span> <span data-ttu-id="bb06a-125">请使用可以记住的强密码，这样就不必记录密码了。</span><span class="sxs-lookup"><span data-stu-id="bb06a-125">Use a strong password that you can remember so that you don't have to write it down.</span></span></p>
</td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="bb06a-126">说明</span><span class="sxs-lookup"><span data-stu-id="bb06a-126">Remarks</span></span>

<span data-ttu-id="bb06a-127">BstrOld 和 bstrNew 字符串长度最多为 20 个字符，并且可以包括除 ASCII 字符 0 (null) 的任何字符。</span><span class="sxs-lookup"><span data-stu-id="bb06a-127">The bstrOld and bstrNew strings can be up to 20 characters long and can include any characters except the ASCII character 0 (null).</span></span> <span data-ttu-id="bb06a-128">若要清除密码，请使用零长度字符串 ("") 的 bstrNew。</span><span class="sxs-lookup"><span data-stu-id="bb06a-128">To clear the password, use a zero-length string ("") for bstrNew.</span></span>

<span data-ttu-id="bb06a-129">密码区分大小写。</span><span class="sxs-lookup"><span data-stu-id="bb06a-129">Passwords are case-sensitive.</span></span>

<span data-ttu-id="bb06a-130">如果数据库没有密码，Microsoft Access 数据库引擎将通过传递旧密码的零长度字符串 ("") 自动创建一个密码。</span><span class="sxs-lookup"><span data-stu-id="bb06a-130">If a database has no password, the Microsoft Access database engine will automatically create one by passing a zero-length string ("") for the old password.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="bb06a-131">[!重要信息] 如果丢失了密码，则永远不能再次打开数据库。</span><span class="sxs-lookup"><span data-stu-id="bb06a-131">If you lose your password, you can never open the database again.</span></span>


