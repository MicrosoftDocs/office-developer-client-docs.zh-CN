---
title: QueryDef.Updatable Property (DAO)
TOCTitle: Updatable Property
ms:assetid: 9b978b7d-1d76-ff27-a032-dd94660fb088
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198056(v=office.15)
ms:contentKeyID: 48546575
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4ad761c2941cb556ce67c9f716247663220f753f
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25873689"
---
# <a name="querydefupdatable-property-dao"></a><span data-ttu-id="b9157-102">QueryDef.Updatable Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="b9157-102">QueryDef.Updatable Property (DAO)</span></span>


<span data-ttu-id="b9157-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b9157-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b9157-p101">返回一个值，该值指示是否可以更改 DAO 对象。只读 **Boolean**。</span><span class="sxs-lookup"><span data-stu-id="b9157-p101">Returns a value that indicates whether you can change a DAO object. Read-only **Boolean**.</span></span>

## <a name="syntax"></a><span data-ttu-id="b9157-106">语法</span><span class="sxs-lookup"><span data-stu-id="b9157-106">Syntax</span></span>

<span data-ttu-id="b9157-107">*表达式*。可更新</span><span class="sxs-lookup"><span data-stu-id="b9157-107">*expression* .Updatable</span></span>

<span data-ttu-id="b9157-108">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="b9157-108">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="b9157-109">注解</span><span class="sxs-lookup"><span data-stu-id="b9157-109">Remarks</span></span>

<span data-ttu-id="b9157-110">即使生成的 \*\*\*\*Recordset\*\*\*\* 对象不可更新，如果可以更新查询定义，也将 **QueryDef** 对象的 [Updatable](recordset-object-dao.md) 属性设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="b9157-110">The **Updatable** property of a **QueryDef** object is set to **True** if the query definition can be updated, even if the resulting **[Recordset](recordset-object-dao.md)** object isn't updatable.</span></span>

