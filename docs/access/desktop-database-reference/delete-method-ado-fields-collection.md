---
title: Delete 方法（ADO Fields 集合）
TOCTitle: Delete Method (ADO Fields Collection)
ms:assetid: adc66365-703f-4491-fc5b-dbc9bca2ac53
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249817(v=office.15)
ms:contentKeyID: 48547047
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0fc2e614916026effe6ee0a9766e0b23db200574
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25886394"
---
# <a name="delete-method-ado-fields-collection"></a><span data-ttu-id="60c8a-102">Delete 方法（ADO Fields 集合）</span><span class="sxs-lookup"><span data-stu-id="60c8a-102">Delete Method (ADO Fields Collection)</span></span>


<span data-ttu-id="60c8a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="60c8a-103">**Applies to**: Access 2013, Office 2013</span></span>



<span data-ttu-id="60c8a-104">用于从 [Fields](fields-collection-ado.md) 集合中删除对象。</span><span class="sxs-lookup"><span data-stu-id="60c8a-104">Deletes an object from the [Fields](fields-collection-ado.md) collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="60c8a-105">语法</span><span class="sxs-lookup"><span data-stu-id="60c8a-105">Syntax</span></span>

<span data-ttu-id="60c8a-106">*字段*。删除*字段*</span><span class="sxs-lookup"><span data-stu-id="60c8a-106">*Fields*.Delete*Field*</span></span>

## <a name="parameters"></a><span data-ttu-id="60c8a-107">参数</span><span class="sxs-lookup"><span data-stu-id="60c8a-107">Parameters</span></span>

  - <span data-ttu-id="60c8a-108">*Field*</span><span class="sxs-lookup"><span data-stu-id="60c8a-108">*Field*</span></span>

  - <span data-ttu-id="60c8a-p101">**变量型** ，指定要删除的 [Field](field-object-ado.md) 对象。此参数可以是 **Field** 对象的名称，或 **Field** 对象自身的序号位置。</span><span class="sxs-lookup"><span data-stu-id="60c8a-p101">A **Variant** that designates the [Field](field-object-ado.md) object to delete. This parameter can be the name of the **Field** object or the ordinal position of the **Field** object itself.</span></span>

## <a name="remarks"></a><span data-ttu-id="60c8a-111">备注</span><span class="sxs-lookup"><span data-stu-id="60c8a-111">Remarks</span></span>

<span data-ttu-id="60c8a-112">对打开的 **Recordset** 调用 [Fields.Delete](recordset-object-ado.md) 方法会引发运行时错误。</span><span class="sxs-lookup"><span data-stu-id="60c8a-112">Calling the **Fields.Delete** method on an open [Recordset](recordset-object-ado.md) causes a run-time error.</span></span>

