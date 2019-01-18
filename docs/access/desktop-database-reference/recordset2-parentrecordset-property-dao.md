---
title: Recordset2.ParentRecordset 属性 (DAO)
TOCTitle: ParentRecordset Property
ms:assetid: 816cc92e-e530-6ca6-65b0-3165221835a6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196492(v=office.15)
ms:contentKeyID: 48545948
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1101188
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 7424e31e7f351af02bdd54bd06fe41f7db5b5f54
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28722121"
---
# <a name="recordset2parentrecordset-property-dao"></a><span data-ttu-id="07294-102">Recordset2.ParentRecordset 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="07294-102">Recordset2.ParentRecordset property (DAO)</span></span>


<span data-ttu-id="07294-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="07294-103">**Applies to**: Access 2013, Office 2013</span></span> 

<span data-ttu-id="07294-p101">返回指定记录集的父 **Recordset**。只读。</span><span class="sxs-lookup"><span data-stu-id="07294-p101">Returns the parent **Recordset** of the specified recordset. Read-only.</span></span>

## <a name="version-information"></a><span data-ttu-id="07294-106">版本信息</span><span class="sxs-lookup"><span data-stu-id="07294-106">Version information</span></span>

<span data-ttu-id="07294-107">添加的版本： Access 2007</span><span class="sxs-lookup"><span data-stu-id="07294-107">Version added: Access 2007</span></span>

## <a name="syntax"></a><span data-ttu-id="07294-108">语法</span><span class="sxs-lookup"><span data-stu-id="07294-108">Syntax</span></span>

<span data-ttu-id="07294-109">*表达式*。ParentRecordset</span><span class="sxs-lookup"><span data-stu-id="07294-109">*expression* .ParentRecordset</span></span>

<span data-ttu-id="07294-110">*表达式*一个表示**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="07294-110">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="07294-111">注解</span><span class="sxs-lookup"><span data-stu-id="07294-111">Remarks</span></span>

<span data-ttu-id="07294-112">如果指定记录集不代表多值字段，则 **ParentRecordset** 属性将返回 **Null**。</span><span class="sxs-lookup"><span data-stu-id="07294-112">The **ParentRecordset** property returns **Null** if the specifed recordset does not represent a multi-valued field.</span></span>

