---
title: TableDef.RecordCount 属性 (DAO)
TOCTitle: RecordCount Property
ms:assetid: f8804244-0134-fc1f-1f5f-4971afe17974
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836946(v=office.15)
ms:contentKeyID: 48548783
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 5eb9588927c9e35fea54964f16150735a7374cd5
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28722863"
---
# <a name="tabledefrecordcount-property-dao"></a><span data-ttu-id="fb160-102">TableDef.RecordCount 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="fb160-102">TableDef.RecordCount property (DAO)</span></span>


<span data-ttu-id="fb160-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="fb160-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="fb160-p101">返回 **[TableDef](tabledef-object-dao.md)** 对象中的总记录数。 **Long** 类型，只读。</span><span class="sxs-lookup"><span data-stu-id="fb160-p101">Returns the total number of records in a **[TableDef](tabledef-object-dao.md)** object. Read-only **Long**.</span></span>

## <a name="syntax"></a><span data-ttu-id="fb160-106">语法</span><span class="sxs-lookup"><span data-stu-id="fb160-106">Syntax</span></span>

<span data-ttu-id="fb160-107">*表达式*。RecordCount</span><span class="sxs-lookup"><span data-stu-id="fb160-107">*expression* .RecordCount</span></span>

<span data-ttu-id="fb160-108">*表达式*一个代表**TableDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="fb160-108">*expression* A variable that represents a **TableDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="fb160-109">注解</span><span class="sxs-lookup"><span data-stu-id="fb160-109">Remarks</span></span>

<span data-ttu-id="fb160-110">如果 **Recordset** 或 **TableDef** 对象不含记录，则其 **RecordCount** 属性设置为 0。</span><span class="sxs-lookup"><span data-stu-id="fb160-110">A **Recordset** or **TableDef** object with no records has a **RecordCount** property setting of 0.</span></span>

<span data-ttu-id="fb160-111">当使用链接的 **TableDef** 对象时，**RecordCount** 属性设置始终为 -1。</span><span class="sxs-lookup"><span data-stu-id="fb160-111">When you work with linked**TableDef** objects, the **RecordCount** property setting is always –1.</span></span>

