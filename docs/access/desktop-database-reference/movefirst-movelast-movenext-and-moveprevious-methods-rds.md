---
title: MoveFirst、MoveLast、MoveNext 和 MovePrevious 方法 (RDS)
TOCTitle: MoveFirst, MoveLast, MoveNext, and MovePrevious Methods (RDS)
ms:assetid: 32ef8fa9-c096-b4e7-3396-b88a6a9bd1a2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249101(v=office.15)
ms:contentKeyID: 48544092
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f4671e57e3edb44bc1c927ca11f2cf79e70c2699
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467411"
---
# <a name="movefirst-movelast-movenext-and-moveprevious-methods-rds"></a><span data-ttu-id="27ade-102">MoveFirst、MoveLast、MoveNext 和 MovePrevious 方法 (RDS)</span><span class="sxs-lookup"><span data-stu-id="27ade-102">MoveFirst, MoveLast, MoveNext, and MovePrevious Methods (RDS)</span></span>


<span data-ttu-id="27ade-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="27ade-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="27ade-104">用于移动到指定的 [Recordset](recordset-object-ado.md) 对象中的第一个、最后一个、下一个或上一个记录。</span><span class="sxs-lookup"><span data-stu-id="27ade-104">Moves to the first, last, next, or previous record in a specified [Recordset](recordset-object-ado.md) object.</span></span>

## <a name="syntax"></a><span data-ttu-id="27ade-105">语法</span><span class="sxs-lookup"><span data-stu-id="27ade-105">Syntax</span></span>

<span data-ttu-id="27ade-106">*DataControl*。记录集。{</span><span class="sxs-lookup"><span data-stu-id="27ade-106">*DataControl*.Recordset.{</span></span> <span data-ttu-id="27ade-107">MoveFirst |MoveLast |MoveNext |MovePrevious}</span><span class="sxs-lookup"><span data-stu-id="27ade-107">MoveFirst | MoveLast | MoveNext | MovePrevious}</span></span>

## <a name="parameters"></a><span data-ttu-id="27ade-108">参数</span><span class="sxs-lookup"><span data-stu-id="27ade-108">Parameters</span></span>

  - <span data-ttu-id="27ade-109">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="27ade-109">*DataControl*</span></span>

  - <span data-ttu-id="27ade-110">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="27ade-110">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>

## <a name="remarks"></a><span data-ttu-id="27ade-111">说明</span><span class="sxs-lookup"><span data-stu-id="27ade-111">Remarks</span></span>

<span data-ttu-id="27ade-p102">可以将 **Move** 方法用于 **RDS.DataControl** 对象以便在网页上数据绑定的控件中的数据记录中导航。例如，假设通过绑定到一个 **RDS.DataControl** 对象在网格中显示 **Recordset** 。然后，可以包括"第一个"、"最后一个"、"下一个"和"上一个"按钮，用户单击这些按钮可以分别移动到所显示的 **Recordset** 中的第一个、最后一个、下一个或上一个记录。通过在 onClick 过程中分别调用对应于"第一个"、"最后一个"、"下一个"和"上一个"按钮的 **RDS.DataControl** 对象的 **MoveFirst** 、 **MoveLast** 、 **MoveNext** 和 **MovePrevious** 方法来实现该目的。 [通讯簿示例](address-book-navigation-buttons.md)显示了如何执行该操作。</span><span class="sxs-lookup"><span data-stu-id="27ade-p102">You can use the **Move** methods with the **RDS.DataControl** object to navigate through the data records in the data-bound controls on a Web page. For example, suppose you display a **Recordset** in a grid by binding to an **RDS.DataControl** object. You can then include First, Last, Next, and Previous buttons that users can click to move to the first, last, next, or previous record in the displayed **Recordset**. You do this by calling the **MoveFirst**, **MoveLast**, **MoveNext**, and **MovePrevious** methods of the **RDS.DataControl** object in the onClick procedures for the First, Last, Next, and Previous buttons, respectively. The [Address Book example](address-book-navigation-buttons.md) shows how to do this.</span></span>

