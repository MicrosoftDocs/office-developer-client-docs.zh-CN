---
title: QueryDef 可更新属性 (DAO)
TOCTitle: Updatable Property
ms:assetid: 9b978b7d-1d76-ff27-a032-dd94660fb088
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198056(v=office.15)
ms:contentKeyID: 48546575
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c5321e834f1dd5ed663033cacb530962d7beeb5a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303330"
---
# <a name="querydefupdatable-property-dao"></a><span data-ttu-id="cfb46-102">QueryDef 可更新属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="cfb46-102">QueryDef.Updatable property (DAO)</span></span>


<span data-ttu-id="cfb46-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="cfb46-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="cfb46-104">返回一个值，该值指示是否可以更改 DAO 对象。</span><span class="sxs-lookup"><span data-stu-id="cfb46-104">Returns a value that indicates whether you can change a DAO object.</span></span> <span data-ttu-id="cfb46-105">只读 **Boolean** 类型。</span><span class="sxs-lookup"><span data-stu-id="cfb46-105">Read-only **Boolean**.</span></span>

## <a name="syntax"></a><span data-ttu-id="cfb46-106">语法</span><span class="sxs-lookup"><span data-stu-id="cfb46-106">Syntax</span></span>

<span data-ttu-id="cfb46-107">*表达式*。更新</span><span class="sxs-lookup"><span data-stu-id="cfb46-107">*expression* .Updatable</span></span>

<span data-ttu-id="cfb46-108">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="cfb46-108">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="cfb46-109">注解</span><span class="sxs-lookup"><span data-stu-id="cfb46-109">Remarks</span></span>

<span data-ttu-id="cfb46-110">即使生成的 **[Recordset](recordset-object-dao.md)** 对象不可更新，如果可以更新查询定义，也将 **QueryDef** 对象的 **Updatable** 属性设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="cfb46-110">The **Updatable** property of a **QueryDef** object is set to **True** if the query definition can be updated, even if the resulting **[Recordset](recordset-object-dao.md)** object isn't updatable.</span></span>

