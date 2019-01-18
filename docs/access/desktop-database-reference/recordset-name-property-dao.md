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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28721428"
---
# <a name="recordsetname-property-dao"></a><span data-ttu-id="0c478-102">Recordset.Name 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="0c478-102">Recordset.Name property (DAO)</span></span>


<span data-ttu-id="0c478-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="0c478-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0c478-p101">返回指定对象的名称。只读 **String**。</span><span class="sxs-lookup"><span data-stu-id="0c478-p101">Returns the name of the specified object. Read-only **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="0c478-106">语法</span><span class="sxs-lookup"><span data-stu-id="0c478-106">Syntax</span></span>

<span data-ttu-id="0c478-107">*表达式*。名称</span><span class="sxs-lookup"><span data-stu-id="0c478-107">*expression* .Name</span></span>

<span data-ttu-id="0c478-108">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="0c478-108">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="0c478-109">注解</span><span class="sxs-lookup"><span data-stu-id="0c478-109">Remarks</span></span>

<span data-ttu-id="0c478-110">使用 SQL 语句打开的 **Recordset** 对象的 **Name** 属性是 SQL 语句的前 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="0c478-110">The **Name** property of a **Recordset** object opened by using an SQL statement is the first 256 characters of the SQL statement.</span></span>

