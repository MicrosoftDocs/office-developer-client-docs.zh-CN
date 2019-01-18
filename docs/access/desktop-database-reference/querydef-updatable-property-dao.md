---
title: QueryDef.Updatable 属性 (DAO)
TOCTitle: Updatable Property
ms:assetid: 9b978b7d-1d76-ff27-a032-dd94660fb088
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198056(v=office.15)
ms:contentKeyID: 48546575
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c5321e834f1dd5ed663033cacb530962d7beeb5a
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28713364"
---
# <a name="querydefupdatable-property-dao"></a><span data-ttu-id="8307a-102">QueryDef.Updatable 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="8307a-102">QueryDef.Updatable property (DAO)</span></span>


<span data-ttu-id="8307a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="8307a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8307a-p101">返回一个值，该值指示是否可以更改 DAO 对象。只读 **Boolean**。</span><span class="sxs-lookup"><span data-stu-id="8307a-p101">Returns a value that indicates whether you can change a DAO object. Read-only **Boolean**.</span></span>

## <a name="syntax"></a><span data-ttu-id="8307a-106">语法</span><span class="sxs-lookup"><span data-stu-id="8307a-106">Syntax</span></span>

<span data-ttu-id="8307a-107">*表达式*。可更新</span><span class="sxs-lookup"><span data-stu-id="8307a-107">*expression* .Updatable</span></span>

<span data-ttu-id="8307a-108">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="8307a-108">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="8307a-109">注解</span><span class="sxs-lookup"><span data-stu-id="8307a-109">Remarks</span></span>

<span data-ttu-id="8307a-110">即使生成的 \*\*\*\*Recordset\*\*\*\* 对象不可更新，如果可以更新查询定义，也将 **QueryDef** 对象的 [Updatable](recordset-object-dao.md) 属性设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="8307a-110">The **Updatable** property of a **QueryDef** object is set to **True** if the query definition can be updated, even if the resulting **[Recordset](recordset-object-dao.md)** object isn't updatable.</span></span>

