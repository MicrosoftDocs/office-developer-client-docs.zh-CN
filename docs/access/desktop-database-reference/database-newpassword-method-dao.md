---
title: NewPassword 方法 (DAO)
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
localization_priority: Normal
ms.openlocfilehash: 20f09dbfba50526409472f7eb804ba2c47e4d1d5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294853"
---
# <a name="databasenewpassword-method-dao"></a><span data-ttu-id="836dc-102">NewPassword 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="836dc-102">Database.NewPassword method (DAO)</span></span>

<span data-ttu-id="836dc-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="836dc-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="836dc-104">更改现有 Microsoft Access 数据库引擎数据库的密码（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="836dc-104">Changes the password of an existing Microsoft Access database engine database (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="836dc-105">语法</span><span class="sxs-lookup"><span data-stu-id="836dc-105">Syntax</span></span>

<span data-ttu-id="836dc-106">*表达式*。NewPassword (***bstrOld***, ***bstrNew***)</span><span class="sxs-lookup"><span data-stu-id="836dc-106">*expression* .NewPassword(***bstrOld***, ***bstrNew***)</span></span>

<span data-ttu-id="836dc-107">*表达式*一个返回**Database**对象的表达式。</span><span class="sxs-lookup"><span data-stu-id="836dc-107">*expression* An expression that returns a **Database** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="836dc-108">参数</span><span class="sxs-lookup"><span data-stu-id="836dc-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="836dc-109">名称</span><span class="sxs-lookup"><span data-stu-id="836dc-109">Name</span></span></p></th>
<th><p><span data-ttu-id="836dc-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="836dc-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="836dc-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="836dc-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="836dc-112">说明</span><span class="sxs-lookup"><span data-stu-id="836dc-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="836dc-113"><em>bstrOld</em></span><span class="sxs-lookup"><span data-stu-id="836dc-113"><em>bstrOld</em></span></span></p></td>
<td><p><span data-ttu-id="836dc-114">必需</span><span class="sxs-lookup"><span data-stu-id="836dc-114">Required</span></span></p></td>
<td><p><span data-ttu-id="836dc-115"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="836dc-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="836dc-116"><strong>Database</strong> 对象的 <strong>Password</strong> 属性的当前设置。</span><span class="sxs-lookup"><span data-stu-id="836dc-116">The current setting of the <strong>Password</strong> property of the <strong>Database</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="836dc-117"><em>bstrNew</em></span><span class="sxs-lookup"><span data-stu-id="836dc-117"><em>bstrNew</em></span></span></p></td>
<td><p><span data-ttu-id="836dc-118">必需</span><span class="sxs-lookup"><span data-stu-id="836dc-118">Required</span></span></p></td>
<td><p><span data-ttu-id="836dc-119"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="836dc-119"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="836dc-120"><strong>Database</strong>对象的<strong>Password</strong>属性的新设置。</span><span class="sxs-lookup"><span data-stu-id="836dc-120">The new setting of the <strong>Password</strong> property of the <strong>Database</strong> object.</span></span></p>
<p><span data-ttu-id="836dc-121"><strong>注意</strong>: 请使用组合了大小写字母、数字和符号的强密码。</span><span class="sxs-lookup"><span data-stu-id="836dc-121"><strong>NOTE</strong>: Use strong passwords that combine upper- and lowercase letters, numbers, and symbols.</span></span> <span data-ttu-id="836dc-122">弱密码不会混合这些元素。</span><span class="sxs-lookup"><span data-stu-id="836dc-122">Weak passwords don't mix these elements.</span></span> <span data-ttu-id="836dc-123">强密码：Y6dh!et5。</span><span class="sxs-lookup"><span data-stu-id="836dc-123">Strong password: Y6dh!et5.</span></span> <span data-ttu-id="836dc-124">弱密码：House27。</span><span class="sxs-lookup"><span data-stu-id="836dc-124">Weak password: House27.</span></span> <span data-ttu-id="836dc-125">请使用可以记住的强密码，这样就不必记录密码了。</span><span class="sxs-lookup"><span data-stu-id="836dc-125">Use a strong password that you can remember so that you don't have to write it down.</span></span></p>
</td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="836dc-126">注解</span><span class="sxs-lookup"><span data-stu-id="836dc-126">Remarks</span></span>

<span data-ttu-id="836dc-127">bstrOld 和 bstrNew 字符串的长度最多为20个字符, 并且可以包含除 ASCII 字符 0 (null) 以外的任何字符。</span><span class="sxs-lookup"><span data-stu-id="836dc-127">The bstrOld and bstrNew strings can be up to 20 characters long and can include any characters except the ASCII character 0 (null).</span></span> <span data-ttu-id="836dc-128">若要清除密码, 请对 bstrNew 使用零长度字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="836dc-128">To clear the password, use a zero-length string ("") for bstrNew.</span></span>

<span data-ttu-id="836dc-129">密码区分大小写。</span><span class="sxs-lookup"><span data-stu-id="836dc-129">Passwords are case-sensitive.</span></span>

<span data-ttu-id="836dc-130">如果数据库没有密码，Microsoft Access 数据库引擎将通过传递旧密码的零长度字符串 ("") 自动创建一个密码。</span><span class="sxs-lookup"><span data-stu-id="836dc-130">If a database has no password, the Microsoft Access database engine will automatically create one by passing a zero-length string ("") for the old password.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="836dc-131">[!重要信息] 如果丢失了密码，则永远不能再次打开数据库。</span><span class="sxs-lookup"><span data-stu-id="836dc-131">If you lose your password, you can never open the database again.</span></span>


