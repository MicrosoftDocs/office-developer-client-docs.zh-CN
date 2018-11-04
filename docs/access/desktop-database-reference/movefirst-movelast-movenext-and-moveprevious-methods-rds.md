---
title: MoveFirst、MoveLast、MoveNext 和 MovePrevious 方法 (RDS)
TOCTitle: MoveFirst, MoveLast, MoveNext, and MovePrevious methods (RDS)
ms:assetid: 32ef8fa9-c096-b4e7-3396-b88a6a9bd1a2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249101(v=office.15)
ms:contentKeyID: 48544092
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ac3daa25f933438ad09b5af3c4b383bb19461cb2
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949246"
---
# <a name="movefirst-movelast-movenext-and-moveprevious-methods-rds"></a><span data-ttu-id="3ef63-102">MoveFirst、MoveLast、MoveNext 和 MovePrevious 方法 (RDS)</span><span class="sxs-lookup"><span data-stu-id="3ef63-102">MoveFirst, MoveLast, MoveNext, and MovePrevious methods (RDS)</span></span>

<span data-ttu-id="3ef63-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="3ef63-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="3ef63-104">用于移动到指定的 [Recordset](recordset-object-ado.md) 对象中的第一个、最后一个、下一个或上一个记录。</span><span class="sxs-lookup"><span data-stu-id="3ef63-104">Moves to the first, last, next, or previous record in a specified [Recordset](recordset-object-ado.md) object.</span></span>

## <a name="syntax"></a><span data-ttu-id="3ef63-105">语法</span><span class="sxs-lookup"><span data-stu-id="3ef63-105">Syntax</span></span>

<span data-ttu-id="3ef63-106">*DataControl*。记录集。{</span><span class="sxs-lookup"><span data-stu-id="3ef63-106">*DataControl*.Recordset.{</span></span> <span data-ttu-id="3ef63-107">MoveFirst |MoveLast |MoveNext |MovePrevious}</span><span class="sxs-lookup"><span data-stu-id="3ef63-107">MoveFirst | MoveLast | MoveNext | MovePrevious}</span></span>

## <a name="parameters"></a><span data-ttu-id="3ef63-108">参数</span><span class="sxs-lookup"><span data-stu-id="3ef63-108">Parameters</span></span>

|<span data-ttu-id="3ef63-109">参数</span><span class="sxs-lookup"><span data-stu-id="3ef63-109">Parameter</span></span>|<span data-ttu-id="3ef63-110">说明</span><span class="sxs-lookup"><span data-stu-id="3ef63-110">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="3ef63-111">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="3ef63-111">*DataControl*</span></span> |<span data-ttu-id="3ef63-112">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="3ef63-112">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3ef63-113">说明</span><span class="sxs-lookup"><span data-stu-id="3ef63-113">Remarks</span></span>

<span data-ttu-id="3ef63-114">您可以使用**Move**方法与**rds.DataControl**对象浏览网页上的数据绑定控件中的数据记录。</span><span class="sxs-lookup"><span data-stu-id="3ef63-114">You can use the **Move** methods with the **RDS.DataControl** object to navigate through the data records in the data-bound controls on a webpage.</span></span> 

<span data-ttu-id="3ef63-115">例如，假设通过绑定到一个 **RDS.DataControl** 对象在网格中显示 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="3ef63-115">For example, suppose you display a **Recordset** in a grid by binding to an **RDS.DataControl** object.</span></span> <span data-ttu-id="3ef63-116">然后，可以包括"第一个"、"最后一个"、"下一个"和"上一个"按钮，用户单击这些按钮可以分别移动到所显示的 **Recordset** 中的第一个、最后一个、下一个或上一个记录。</span><span class="sxs-lookup"><span data-stu-id="3ef63-116">You can then include First, Last, Next, and Previous buttons that users can click to move to the first, last, next, or previous record in the displayed **Recordset**.</span></span> <span data-ttu-id="3ef63-117">通过在 onClick 过程中分别调用对应于"第一个"、"最后一个"、"下一个"和"上一个"按钮的 **RDS.DataControl** 对象的 **MoveFirst** 、 **MoveLast** 、 **MoveNext** 和 **MovePrevious** 方法来实现该目的。</span><span class="sxs-lookup"><span data-stu-id="3ef63-117">You do this by calling the **MoveFirst**, **MoveLast**, **MoveNext**, and **MovePrevious** methods of the **RDS.DataControl** object in the onClick procedures for the First, Last, Next, and Previous buttons, respectively.</span></span> <span data-ttu-id="3ef63-118">[通讯簿示例](address-book-navigation-buttons.md)显示了如何执行该操作。</span><span class="sxs-lookup"><span data-stu-id="3ef63-118">The [Address Book example](address-book-navigation-buttons.md) shows how to do this.</span></span>

