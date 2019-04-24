---
title: State 属性 (ADO MD)
TOCTitle: State property (ADO MD)
ms:assetid: 4df09f45-9b62-33ce-b4ed-230e41eaac7a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249249(v=office.15)
ms:contentKeyID: 48544744
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 051a9f0cc50ae3a60edb033f6807f72fc0688976
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306361"
---
# <a name="state-property-ado-md"></a><span data-ttu-id="f4b5c-102">State 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="f4b5c-102">State property (ADO MD)</span></span>


<span data-ttu-id="f4b5c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="f4b5c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f4b5c-104">指示单元格集的当前状态。</span><span class="sxs-lookup"><span data-stu-id="f4b5c-104">Indicates the current state of the cellset.</span></span>

## <a name="return-values"></a><span data-ttu-id="f4b5c-105">返回值</span><span class="sxs-lookup"><span data-stu-id="f4b5c-105">Return values</span></span>

<span data-ttu-id="f4b5c-106">返回一个 **Long** 整数值，该值指示 [Cellset](cellset-object-ado-md.md) 对象的当前状况，并且为只读。</span><span class="sxs-lookup"><span data-stu-id="f4b5c-106">Returns a **Long** integer indicating the current condition of the [Cellset](cellset-object-ado-md.md) object and is read-only.</span></span> <span data-ttu-id="f4b5c-107">以下属性值有效：**adStateClosed** (0) 和 **adStateOpen** (1)。</span><span class="sxs-lookup"><span data-stu-id="f4b5c-107">The following values are valid: **adStateClosed** (0) and **adStateOpen** (1).</span></span>

## <a name="remarks"></a><span data-ttu-id="f4b5c-108">注解</span><span class="sxs-lookup"><span data-stu-id="f4b5c-108">Remarks</span></span>

<span data-ttu-id="f4b5c-p102">若要使用 [ObjectStateEnum](objectstateenum.md) 常量名称，必须在项目中引用 ADO 类型库。有关更多信息，请参阅[将 ADO 与 ADO MD 结合使用](using-ado-with-ado-md.md)。</span><span class="sxs-lookup"><span data-stu-id="f4b5c-p102">To use the [ObjectStateEnum](objectstateenum.md) constant names, you must have the ADO type library referenced in your project. See [Using ADO with ADO MD](using-ado-with-ado-md.md) for more information.</span></span>

