---
title: Recordset.Name 属性 (DAO)
TOCTitle: Name Property
ms:assetid: 2a80b994-a135-cd61-3906-17dfa0580110
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192067(v=office.15)
ms:contentKeyID: 48543910
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 36e66bc377846259b1e7279a1563e3862ea9c0eb
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25930901"
---
# <a name="recordsetname-property-dao"></a><span data-ttu-id="c3ca8-102">Recordset.Name 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="c3ca8-102">Recordset.Name property (DAO)</span></span>


<span data-ttu-id="c3ca8-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c3ca8-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c3ca8-p101">返回指定对象的名称。只读 **String**。</span><span class="sxs-lookup"><span data-stu-id="c3ca8-p101">Returns the name of the specified object. Read-only **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="c3ca8-106">语法</span><span class="sxs-lookup"><span data-stu-id="c3ca8-106">Syntax</span></span>

<span data-ttu-id="c3ca8-107">*表达式*。名称</span><span class="sxs-lookup"><span data-stu-id="c3ca8-107">*expression* .Name</span></span>

<span data-ttu-id="c3ca8-108">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="c3ca8-108">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="c3ca8-109">注解</span><span class="sxs-lookup"><span data-stu-id="c3ca8-109">Remarks</span></span>

<span data-ttu-id="c3ca8-110">使用 SQL 语句打开的 **Recordset** 对象的 **Name** 属性是 SQL 语句的前 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="c3ca8-110">The **Name** property of a **Recordset** object opened by using an SQL statement is the first 256 characters of the SQL statement.</span></span>

