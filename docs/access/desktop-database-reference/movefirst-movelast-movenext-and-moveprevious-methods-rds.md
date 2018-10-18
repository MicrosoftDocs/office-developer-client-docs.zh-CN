---
title: MoveFirst、MoveLast、MoveNext 和 MovePrevious 方法 (RDS)
TOCTitle: MoveFirst, MoveLast, MoveNext, and MovePrevious Methods (RDS)
ms:assetid: 32ef8fa9-c096-b4e7-3396-b88a6a9bd1a2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249101(v=office.15)
ms:contentKeyID: 48544092
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 02c6bc5ab4cc8357d7f349eb1698c2e6a026e173
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25602851"
---
# <a name="movefirst-movelast-movenext-and-moveprevious-methods-rds"></a><span data-ttu-id="d0d0b-102">MoveFirst、MoveLast、MoveNext 和 MovePrevious 方法 (RDS)</span><span class="sxs-lookup"><span data-stu-id="d0d0b-102">MoveFirst, MoveLast, MoveNext, and MovePrevious Methods (RDS)</span></span>


<span data-ttu-id="d0d0b-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="d0d0b-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="d0d0b-104">用于移动到指定的 [Recordset](recordset-object-ado.md) 对象中的第一个、最后一个、下一个或上一个记录。</span><span class="sxs-lookup"><span data-stu-id="d0d0b-104">Moves to the first, last, next, or previous record in a specified [Recordset](recordset-object-ado.md) object.</span></span>

## <a name="syntax"></a><span data-ttu-id="d0d0b-105">语法</span><span class="sxs-lookup"><span data-stu-id="d0d0b-105">Syntax</span></span>

<span data-ttu-id="d0d0b-106">*DataControl*。记录集。{</span><span class="sxs-lookup"><span data-stu-id="d0d0b-106">*DataControl*.Recordset.{</span></span> <span data-ttu-id="d0d0b-107">MoveFirst |MoveLast |MoveNext |MovePrevious}</span><span class="sxs-lookup"><span data-stu-id="d0d0b-107">MoveFirst | MoveLast | MoveNext | MovePrevious}</span></span>

## <a name="parameters"></a><span data-ttu-id="d0d0b-108">参数</span><span class="sxs-lookup"><span data-stu-id="d0d0b-108">Parameters</span></span>

  - <span data-ttu-id="d0d0b-109">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="d0d0b-109">*DataControl*</span></span>

  - <span data-ttu-id="d0d0b-110">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="d0d0b-110">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>

## <a name="remarks"></a><span data-ttu-id="d0d0b-111">说明</span><span class="sxs-lookup"><span data-stu-id="d0d0b-111">Remarks</span></span>

<span data-ttu-id="d0d0b-112"><<<<<<< 标头您可以使用**Move**方法与**rds.DataControl**对象浏览网页上的数据绑定控件中的数据记录。</span><span class="sxs-lookup"><span data-stu-id="d0d0b-112"><<<<<<< HEAD You can use the **Move** methods with the **RDS.DataControl** object to navigate through the data records in the data-bound controls on a Web page.</span></span> <span data-ttu-id="d0d0b-113">例如，假设通过绑定到一个 **RDS.DataControl** 对象在网格中显示 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="d0d0b-113">For example, suppose you display a **Recordset** in a grid by binding to an **RDS.DataControl** object.</span></span> <span data-ttu-id="d0d0b-114">然后，可以包括"第一个"、"最后一个"、"下一个"和"上一个"按钮，用户单击这些按钮可以分别移动到所显示的 **Recordset** 中的第一个、最后一个、下一个或上一个记录。</span><span class="sxs-lookup"><span data-stu-id="d0d0b-114">You can then include First, Last, Next, and Previous buttons that users can click to move to the first, last, next, or previous record in the displayed **Recordset**.</span></span> <span data-ttu-id="d0d0b-115">通过在 onClick 过程中分别调用对应于"第一个"、"最后一个"、"下一个"和"上一个"按钮的 **RDS.DataControl** 对象的 **MoveFirst** 、 **MoveLast** 、 **MoveNext** 和 **MovePrevious** 方法来实现该目的。</span><span class="sxs-lookup"><span data-stu-id="d0d0b-115">You do this by calling the **MoveFirst**, **MoveLast**, **MoveNext**, and **MovePrevious** methods of the **RDS.DataControl** object in the onClick procedures for the First, Last, Next, and Previous buttons, respectively.</span></span> <span data-ttu-id="d0d0b-116">[通讯簿示例](address-book-navigation-buttons.md)显示了如何执行该操作。</span><span class="sxs-lookup"><span data-stu-id="d0d0b-116">The [Address Book example](address-book-navigation-buttons.md) shows how to do this.</span></span>
<span data-ttu-id="d0d0b-117">=== 您可以使用**Move**方法与**rds.DataControl**对象浏览网页上的数据绑定控件中的数据记录。</span><span class="sxs-lookup"><span data-stu-id="d0d0b-117">======= You can use the **Move** methods with the **RDS.DataControl** object to navigate through the data records in the data-bound controls on a webpage.</span></span> <span data-ttu-id="d0d0b-118">例如，假设通过绑定到一个 **RDS.DataControl** 对象在网格中显示 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="d0d0b-118">For example, suppose you display a **Recordset** in a grid by binding to an **RDS.DataControl** object.</span></span> <span data-ttu-id="d0d0b-119">然后，可以包括"第一个"、"最后一个"、"下一个"和"上一个"按钮，用户单击这些按钮可以分别移动到所显示的 **Recordset** 中的第一个、最后一个、下一个或上一个记录。</span><span class="sxs-lookup"><span data-stu-id="d0d0b-119">You can then include First, Last, Next, and Previous buttons that users can click to move to the first, last, next, or previous record in the displayed **Recordset**.</span></span> <span data-ttu-id="d0d0b-120">通过在 onClick 过程中分别调用对应于"第一个"、"最后一个"、"下一个"和"上一个"按钮的 **RDS.DataControl** 对象的 **MoveFirst** 、 **MoveLast** 、 **MoveNext** 和 **MovePrevious** 方法来实现该目的。</span><span class="sxs-lookup"><span data-stu-id="d0d0b-120">You do this by calling the **MoveFirst**, **MoveLast**, **MoveNext**, and **MovePrevious** methods of the **RDS.DataControl** object in the onClick procedures for the First, Last, Next, and Previous buttons, respectively.</span></span> <span data-ttu-id="d0d0b-121">[通讯簿示例](address-book-navigation-buttons.md)显示了如何执行该操作。</span><span class="sxs-lookup"><span data-stu-id="d0d0b-121">The [Address Book example](address-book-navigation-buttons.md) shows how to do this.</span></span>
>>>>>>> <span data-ttu-id="d0d0b-122">master</span><span class="sxs-lookup"><span data-stu-id="d0d0b-122">master</span></span>

