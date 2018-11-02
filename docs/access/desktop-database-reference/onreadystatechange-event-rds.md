---
title: onReadyStateChange 事件 (RDS)
TOCTitle: onReadyStateChange event (RDS)
ms:assetid: 88102ee5-cca9-8ccb-5aca-55cda71abc4d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249593(v=office.15)
ms:contentKeyID: 48546126
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3e52ef236a5e57efc965a6b3bd8ab6edd7533f2c
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922207"
---
# <a name="onreadystatechange-event-rds"></a><span data-ttu-id="499b2-102">onReadyStateChange 事件 (RDS)</span><span class="sxs-lookup"><span data-stu-id="499b2-102">onReadyStateChange event (RDS)</span></span>


<span data-ttu-id="499b2-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="499b2-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="499b2-104">只要 **ReadyState** 属性的值发生更改，便会调用 [onReadyStateChange](readystate-property-rds.md) 事件。</span><span class="sxs-lookup"><span data-stu-id="499b2-104">The **onReadyStateChange** event is called whenever the value of the [ReadyState](readystate-property-rds.md) property changes.</span></span>

## <a name="syntax"></a><span data-ttu-id="499b2-105">语法</span><span class="sxs-lookup"><span data-stu-id="499b2-105">Syntax</span></span>

<span data-ttu-id="499b2-106">onReadyStateChange</span><span class="sxs-lookup"><span data-stu-id="499b2-106">onReadyStateChange</span></span>

## <a name="parameters"></a><span data-ttu-id="499b2-107">参数</span><span class="sxs-lookup"><span data-stu-id="499b2-107">Parameters</span></span>

<span data-ttu-id="499b2-108">无。</span><span class="sxs-lookup"><span data-stu-id="499b2-108">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="499b2-109">备注</span><span class="sxs-lookup"><span data-stu-id="499b2-109">Remarks</span></span>

<span data-ttu-id="499b2-p101">**ReadyState** 属性反映 [RDS.DataControl](datacontrol-object-rds.md) 对象在以异步方式将数据检索到其 [Recordset](recordset-object-ado.md) 对象中时的进度。使用 **onReadyStateChange** 事件来监视 **ReadyState** 属性中随时发生的变化。这比定期检查属性值效率更高。</span><span class="sxs-lookup"><span data-stu-id="499b2-p101">The **ReadyState** property reflects the progress of an [RDS.DataControl](datacontrol-object-rds.md) object as it asynchronously retrieves data into its [Recordset](recordset-object-ado.md) object. Use the **onReadyStateChange** event to monitor changes in the **ReadyState** property whenever they occur. This is more efficient than periodically checking the property's value.</span></span>

