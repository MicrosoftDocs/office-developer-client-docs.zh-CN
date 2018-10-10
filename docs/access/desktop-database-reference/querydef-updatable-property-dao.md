---
title: QueryDef.Updatable Property (DAO)
TOCTitle: Updatable Property
ms:assetid: 9b978b7d-1d76-ff27-a032-dd94660fb088
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198056(v=office.15)
ms:contentKeyID: 48546575
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6ca30e86bd61bc5459a552423bd451c7b158996d
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465797"
---
# <a name="querydefupdatable-property-dao"></a><span data-ttu-id="c0e42-102">QueryDef.Updatable Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="c0e42-102">QueryDef.Updatable Property (DAO)</span></span>


<span data-ttu-id="c0e42-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c0e42-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c0e42-p101">返回一个值，该值指示是否可以更改 DAO 对象。只读 **Boolean**。</span><span class="sxs-lookup"><span data-stu-id="c0e42-p101">Returns a value that indicates whether you can change a DAO object. Read-only **Boolean**.</span></span>

## <a name="syntax"></a><span data-ttu-id="c0e42-106">语法</span><span class="sxs-lookup"><span data-stu-id="c0e42-106">Syntax</span></span>

<span data-ttu-id="c0e42-107">*表达式*。可更新</span><span class="sxs-lookup"><span data-stu-id="c0e42-107">*expression* .Updatable</span></span>

<span data-ttu-id="c0e42-108">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="c0e42-108">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="c0e42-109">注解</span><span class="sxs-lookup"><span data-stu-id="c0e42-109">Remarks</span></span>

<span data-ttu-id="c0e42-110">即使生成的 \*\*\*\*Recordset\*\*\*\* 对象不可更新，如果可以更新查询定义，也将 **QueryDef** 对象的 [Updatable](recordset-object-dao.md) 属性设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="c0e42-110">The **Updatable** property of a **QueryDef** object is set to **True** if the query definition can be updated, even if the resulting **[Recordset](recordset-object-dao.md)** object isn't updatable.</span></span>

