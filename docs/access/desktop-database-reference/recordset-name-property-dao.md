---
title: Recordset.Name 属性 (DAO)
TOCTitle: Name Property
ms:assetid: 2a80b994-a135-cd61-3906-17dfa0580110
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192067(v=office.15)
ms:contentKeyID: 48543910
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 43f248ba529991190ae3d322a65a158bd9a4e6e1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300376"
---
# <a name="recordsetname-property-dao"></a><span data-ttu-id="50ea7-102">Recordset.Name 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="50ea7-102">Recordset.Name property (DAO)</span></span>


<span data-ttu-id="50ea7-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="50ea7-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="50ea7-104">返回指定对象的名称。</span><span class="sxs-lookup"><span data-stu-id="50ea7-104">Returns the name of the specified object.</span></span> <span data-ttu-id="50ea7-105">只读的 **字符串** 。</span><span class="sxs-lookup"><span data-stu-id="50ea7-105">Read-only **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="50ea7-106">语法</span><span class="sxs-lookup"><span data-stu-id="50ea7-106">Syntax</span></span>

<span data-ttu-id="50ea7-107">*表达式*。别名</span><span class="sxs-lookup"><span data-stu-id="50ea7-107">*expression* .Name</span></span>

<span data-ttu-id="50ea7-108">*表达式*一个代表**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="50ea7-108">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="50ea7-109">注解</span><span class="sxs-lookup"><span data-stu-id="50ea7-109">Remarks</span></span>

<span data-ttu-id="50ea7-110">使用 SQL 语句打开的 **Recordset** 对象的 **Name** 属性是 SQL 语句的前 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="50ea7-110">The **Name** property of a **Recordset** object opened by using an SQL statement is the first 256 characters of the SQL statement.</span></span>

