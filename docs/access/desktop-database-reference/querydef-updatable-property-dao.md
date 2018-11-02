---
title: QueryDef.Updatable 属性 (DAO)
TOCTitle: Updatable Property
ms:assetid: 9b978b7d-1d76-ff27-a032-dd94660fb088
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198056(v=office.15)
ms:contentKeyID: 48546575
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b0c1a85029270641a944d822ee81954ca1f2528e
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25919806"
---
# <a name="querydefupdatable-property-dao"></a><span data-ttu-id="dc32b-102">QueryDef.Updatable 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="dc32b-102">QueryDef.Updatable property (DAO)</span></span>


<span data-ttu-id="dc32b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="dc32b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="dc32b-p101">返回一个值，该值指示是否可以更改 DAO 对象。只读 **Boolean**。</span><span class="sxs-lookup"><span data-stu-id="dc32b-p101">Returns a value that indicates whether you can change a DAO object. Read-only **Boolean**.</span></span>

## <a name="syntax"></a><span data-ttu-id="dc32b-106">语法</span><span class="sxs-lookup"><span data-stu-id="dc32b-106">Syntax</span></span>

<span data-ttu-id="dc32b-107">*表达式*。可更新</span><span class="sxs-lookup"><span data-stu-id="dc32b-107">*expression* .Updatable</span></span>

<span data-ttu-id="dc32b-108">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="dc32b-108">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="dc32b-109">注解</span><span class="sxs-lookup"><span data-stu-id="dc32b-109">Remarks</span></span>

<span data-ttu-id="dc32b-110">即使生成的 \*\*\*\*Recordset\*\*\*\* 对象不可更新，如果可以更新查询定义，也将 **QueryDef** 对象的 [Updatable](recordset-object-dao.md) 属性设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="dc32b-110">The **Updatable** property of a **QueryDef** object is set to **True** if the query definition can be updated, even if the resulting **[Recordset](recordset-object-dao.md)** object isn't updatable.</span></span>

