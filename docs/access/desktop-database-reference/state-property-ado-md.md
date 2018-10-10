---
title: State 属性 (ADO MD)
TOCTitle: State Property (ADO MD)
ms:assetid: 4df09f45-9b62-33ce-b4ed-230e41eaac7a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249249(v=office.15)
ms:contentKeyID: 48544744
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a42ade39a50eb5dc40e213d6f4c3f4ed0ba3475e
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467001"
---
# <a name="state-property-ado-md"></a><span data-ttu-id="6bc0a-102">State 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="6bc0a-102">State Property (ADO MD)</span></span>


<span data-ttu-id="6bc0a-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="6bc0a-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="6bc0a-104">指示单元格集的当前状态。</span><span class="sxs-lookup"><span data-stu-id="6bc0a-104">Indicates the current state of the cellset.</span></span>

## <a name="return-values"></a><span data-ttu-id="6bc0a-105">返回值</span><span class="sxs-lookup"><span data-stu-id="6bc0a-105">Return Values</span></span>

<span data-ttu-id="6bc0a-p101">返回一个 **Long** 整数值，该值指示 [Cellset](cellset-object-ado-md.md) 对象的当前状况，并且为只读。以下属性值有效： **adStateClosed** (0) 和 **adStateOpen** (1)。</span><span class="sxs-lookup"><span data-stu-id="6bc0a-p101">Returns a **Long** integer indicating the current condition of the [Cellset](cellset-object-ado-md.md) object and is read-only. The following values are valid: **adStateClosed** (0) and **adStateOpen** (1).</span></span>

## <a name="remarks"></a><span data-ttu-id="6bc0a-108">备注</span><span class="sxs-lookup"><span data-stu-id="6bc0a-108">Remarks</span></span>

<span data-ttu-id="6bc0a-p102">若要使用 [ObjectStateEnum](objectstateenum.md) 常量名称，必须在项目中引用 ADO 类型库。有关更多信息，请参阅 [将 ADO 与 ADO MD 结合使用](using-ado-with-ado-md.md)。</span><span class="sxs-lookup"><span data-stu-id="6bc0a-p102">To use the [ObjectStateEnum](objectstateenum.md) constant names, you must have the ADO type library referenced in your project. See [Using ADO with ADO MD](using-ado-with-ado-md.md) for more information.</span></span>

