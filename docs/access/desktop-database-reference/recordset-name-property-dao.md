---
title: Recordset.Name Property (DAO)
TOCTitle: Name Property
ms:assetid: 2a80b994-a135-cd61-3906-17dfa0580110
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192067(v=office.15)
ms:contentKeyID: 48543910
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 308568676f4ccd929441f9b82ca3b928763ffdb7
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468787"
---
# <a name="recordsetname-property-dao"></a><span data-ttu-id="13618-102">Recordset.Name Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="13618-102">Recordset.Name Property (DAO)</span></span>


<span data-ttu-id="13618-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="13618-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="13618-p101">返回指定对象的名称。只读 **String**。</span><span class="sxs-lookup"><span data-stu-id="13618-p101">Returns the name of the specified object. Read-only **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="13618-106">语法</span><span class="sxs-lookup"><span data-stu-id="13618-106">Syntax</span></span>

<span data-ttu-id="13618-107">*表达式*。名称</span><span class="sxs-lookup"><span data-stu-id="13618-107">*expression* .Name</span></span>

<span data-ttu-id="13618-108">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="13618-108">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="13618-109">注解</span><span class="sxs-lookup"><span data-stu-id="13618-109">Remarks</span></span>

<span data-ttu-id="13618-110">使用 SQL 语句打开的 **Recordset** 对象的 **Name** 属性是 SQL 语句的前 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="13618-110">The **Name** property of a **Recordset** object opened by using an SQL statement is the first 256 characters of the SQL statement.</span></span>

