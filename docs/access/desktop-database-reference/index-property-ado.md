---
title: Index 属性 (ADO)
TOCTitle: Index Property (ADO)
ms:assetid: 4cc00521-dcb4-19b2-2174-6e0e9bd42e62
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249241(v=office.15)
ms:contentKeyID: 48544715
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3658fab0887d0d9b98e41334c2025f29f74338b6
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466134"
---
# <a name="index-property-ado"></a><span data-ttu-id="1a070-102">Index 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="1a070-102">Index Property (ADO)</span></span>


<span data-ttu-id="1a070-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="1a070-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="1a070-104">指示当前对 [Recordset](recordset-object-ado.md) 对象有效的索引的名称。</span><span class="sxs-lookup"><span data-stu-id="1a070-104">Indicates the name of the index currently in effect for a [Recordset](recordset-object-ado.md) object.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="1a070-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="1a070-105">Settings and Return Values</span></span>

<span data-ttu-id="1a070-106">设置或返回一个 **String** 值，该值为索引名称。</span><span class="sxs-lookup"><span data-stu-id="1a070-106">Sets or returns a **String** value, which is the name of the index.</span></span>

## <a name="remarks"></a><span data-ttu-id="1a070-107">备注</span><span class="sxs-lookup"><span data-stu-id="1a070-107">Remarks</span></span>

<span data-ttu-id="1a070-p101">由 **Index** 属性命名的索引必须事先已经在 **Recordset** 对象的基本表上进行声明。即索引必须已在程序中声明为 ADOX [Index](index-object-adox.md) 对象，或在创建基本表时声明。</span><span class="sxs-lookup"><span data-stu-id="1a070-p101">The index named by the **Index** property must have previously been declared on the base table underlying the **Recordset** object. That is, the index must have been declared programmatically either as an ADOX [Index](index-object-adox.md) object, or when the base table was created.</span></span>

<span data-ttu-id="1a070-p102">如果无法设置索引，则会发生运行时错误。以下情况下无法设置 **Index** 属性：</span><span class="sxs-lookup"><span data-stu-id="1a070-p102">A run-time error will occur if the index cannot be set. The **Index** property cannot be set:</span></span>

  - <span data-ttu-id="1a070-112">在 [WillChangeRecordset](willchangerecordset-and-recordsetchangecomplete-events-ado.md) 或 **RecordsetChangeComplete** 事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="1a070-112">Within a [WillChangeRecordset](willchangerecordset-and-recordsetchangecomplete-events-ado.md) or **RecordsetChangeComplete** event handler.</span></span>

  - <span data-ttu-id="1a070-113">如果 **Recordset** 仍在执行某个操作（可由 [State](state-property-ado.md) 属性确定）。</span><span class="sxs-lookup"><span data-stu-id="1a070-113">If the **Recordset** is still executing an operation (which can be determined by the [State](state-property-ado.md) property).</span></span>

  - <span data-ttu-id="1a070-114">如果已通过 **Filter** 属性在 [Recordset](filter-property-ado.md) 上设置了筛选器。</span><span class="sxs-lookup"><span data-stu-id="1a070-114">If a filter has been set on the **Recordset** with the [Filter](filter-property-ado.md) property.</span></span>

<span data-ttu-id="1a070-115">如果关闭了 **Recordset** ，则始终能够成功设置 **Index** 属性，但是如果基础提供程序不支持索引，则 **Recordset** 将无法成功打开，或索引将无法使用。</span><span class="sxs-lookup"><span data-stu-id="1a070-115">The **Index** property can always be set successfully if the **Recordset** is closed, but the **Recordset** will not open successfully, or the index will not be usable, if the underlying provider does not support indexes.</span></span>

<span data-ttu-id="1a070-p103">如果可以设置索引，则可以更改当前行位置。这将会导致 [AbsolutePosition](absoluteposition-property-ado.md) 属性的更新，并会导致生成 **WillChangeRecordset** 、 **RecordsetChangeComplete** 、 [WillMove](willmove-and-movecomplete-events-ado.md) 和 [MoveComplete](willmove-and-movecomplete-events-ado.md) 事件。</span><span class="sxs-lookup"><span data-stu-id="1a070-p103">If the index can be set, the current row position may change. This will cause an update to the [AbsolutePosition](absoluteposition-property-ado.md) property, and the generation of **WillChangeRecordset**, **RecordsetChangeComplete**, [WillMove](willmove-and-movecomplete-events-ado.md), and [MoveComplete](willmove-and-movecomplete-events-ado.md) events.</span></span>

<span data-ttu-id="1a070-p104">如果可以设置索引且 [LockType](locktype-property-ado.md) 属性为 **adLockPessimistic** 或 **adLockOptimistic** ，则将执行隐式 [UpdateBatch](updatebatch-method-ado.md) 操作。这将释放当前组和受影响的组，并释放任何现有的筛选，同时当前行位置将移至重新排序的 **Recordset** 的首行。</span><span class="sxs-lookup"><span data-stu-id="1a070-p104">If the index can be set and the [LockType](locktype-property-ado.md) property is **adLockPessimistic** or **adLockOptimistic**, then an implicit [UpdateBatch](updatebatch-method-ado.md) operation is performed. This releases the current and affected groups. Any existing filter is released, and the current row position is changed to the first row of the reordered **Recordset**.</span></span>

<span data-ttu-id="1a070-121">**Index** 属性与 [Seek](seek-method-ado.md) 方法一起使用。</span><span class="sxs-lookup"><span data-stu-id="1a070-121">The **Index** property is used in conjunction with the [Seek](seek-method-ado.md) method.</span></span> <span data-ttu-id="1a070-122">如果基础提供程序不支持 **Index** 属性（因此也不支持 **Seek** 方法），请考虑使用 [Find](find-method-ado.md) 方法替代。</span><span class="sxs-lookup"><span data-stu-id="1a070-122">If the underlying provider does not support the **Index** property, and thus the **Seek** method, consider using the [Find](find-method-ado.md) method instead.</span></span> <span data-ttu-id="1a070-123">确定**Recordset**对象是否支持使用[支持](supports-method-ado.md)**(adIndex)** 方法的索引。</span><span class="sxs-lookup"><span data-stu-id="1a070-123">Determine whether the **Recordset** object supports indexes with the [Supports](supports-method-ado.md)**(adIndex)** method.</span></span>

<span data-ttu-id="1a070-124">尽管二者均处理索引，但内置 **Index** 属性与动态 [Optimize](optimize-property-dynamic-ado.md) 属性无关。</span><span class="sxs-lookup"><span data-stu-id="1a070-124">The built-in **Index** property is not related to the dynamic [Optimize](optimize-property-dynamic-ado.md) property, although they both deal with indexes.</span></span>

