---
title: State 属性 (ADO)
TOCTitle: State Property (ADO)
ms:assetid: ade0a50c-e2d8-23ac-4ea9-b012fedcd5db
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249819(v=office.15)
ms:contentKeyID: 48547053
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231176
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 2bde03f1d6c7619e8140248b2551002f0453fc9a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468786"
---
# <a name="state-property-ado"></a><span data-ttu-id="cf824-102">State 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="cf824-102">State Property (ADO)</span></span>


<span data-ttu-id="cf824-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="cf824-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="cf824-104">对所有适用的对象，指示其状态是打开还是关闭。</span><span class="sxs-lookup"><span data-stu-id="cf824-104">Indicates for all applicable objects whether the state of the object is open or closed.</span></span>

<span data-ttu-id="cf824-105">对执行异步方法的所有适用对象，指示其当前状态是正在连接、正在执行还是正在检索。</span><span class="sxs-lookup"><span data-stu-id="cf824-105">Indicates for all applicable objects executing an asynchronous method, whether the current state of the object is connecting, executing, or retrieving.</span></span>

## <a name="return-value"></a><span data-ttu-id="cf824-106">返回值</span><span class="sxs-lookup"><span data-stu-id="cf824-106">Return Value</span></span>

<span data-ttu-id="cf824-p101">返回一个 **Long** 值，该值可以为 [ObjectStateEnum](objectstateenum.md) 值之一。默认值是 **adStateClosed** 。</span><span class="sxs-lookup"><span data-stu-id="cf824-p101">Returns a **Long** value that can be an [ObjectStateEnum](objectstateenum.md) value. The default value is **adStateClosed**.</span></span>

## <a name="remarks"></a><span data-ttu-id="cf824-109">备注</span><span class="sxs-lookup"><span data-stu-id="cf824-109">Remarks</span></span>

<span data-ttu-id="cf824-110">可以随时使用 **State** 属性确定给定对象的当前状态。</span><span class="sxs-lookup"><span data-stu-id="cf824-110">You can use the **State** property to determine the current state of a given object at any time.</span></span>

<span data-ttu-id="cf824-p102">对象的 **State** 属性可以是组合值。例如，如果正在执行某个语句，则此属性的值将为 **adStateOpen** 和 **adStateExecuting** 的组合值。</span><span class="sxs-lookup"><span data-stu-id="cf824-p102">The object's **State** property can have a combination of values. For example, if a statement is executing, this property will have a combined value of **adStateOpen** and **adStateExecuting**.</span></span>

<span data-ttu-id="cf824-113">**State** 为只读属性。</span><span class="sxs-lookup"><span data-stu-id="cf824-113">The **State** property is read-only.</span></span>

