---
title: TableDef.RecordCount 属性 (DAO)
TOCTitle: RecordCount Property
ms:assetid: f8804244-0134-fc1f-1f5f-4971afe17974
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836946(v=office.15)
ms:contentKeyID: 48548783
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4b24aaa5aec9b17adc169c67733a19a9077a4930
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25920919"
---
# <a name="tabledefrecordcount-property-dao"></a><span data-ttu-id="aa0fc-102">TableDef.RecordCount 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="aa0fc-102">TableDef.RecordCount property (DAO)</span></span>


<span data-ttu-id="aa0fc-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="aa0fc-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="aa0fc-p101">返回 **[TableDef](tabledef-object-dao.md)** 对象中的总记录数。 **Long** 类型，只读。</span><span class="sxs-lookup"><span data-stu-id="aa0fc-p101">Returns the total number of records in a **[TableDef](tabledef-object-dao.md)** object. Read-only **Long**.</span></span>

## <a name="syntax"></a><span data-ttu-id="aa0fc-106">语法</span><span class="sxs-lookup"><span data-stu-id="aa0fc-106">Syntax</span></span>

<span data-ttu-id="aa0fc-107">*表达式*。RecordCount</span><span class="sxs-lookup"><span data-stu-id="aa0fc-107">*expression* .RecordCount</span></span>

<span data-ttu-id="aa0fc-108">*表达式*一个代表**TableDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="aa0fc-108">*expression* A variable that represents a **TableDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="aa0fc-109">注解</span><span class="sxs-lookup"><span data-stu-id="aa0fc-109">Remarks</span></span>

<span data-ttu-id="aa0fc-110">如果 **Recordset** 或 **TableDef** 对象不含记录，则其 **RecordCount** 属性设置为 0。</span><span class="sxs-lookup"><span data-stu-id="aa0fc-110">A **Recordset** or **TableDef** object with no records has a **RecordCount** property setting of 0.</span></span>

<span data-ttu-id="aa0fc-111">当使用链接的 **TableDef** 对象时，**RecordCount** 属性设置始终为 -1。</span><span class="sxs-lookup"><span data-stu-id="aa0fc-111">When you work with linked**TableDef** objects, the **RecordCount** property setting is always –1.</span></span>

