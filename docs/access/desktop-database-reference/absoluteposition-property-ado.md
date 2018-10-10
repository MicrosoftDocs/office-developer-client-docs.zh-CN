---
title: AbsolutePosition 属性 (ADO)
TOCTitle: AbsolutePosition Property (ADO)
ms:assetid: 500be001-9fa1-177b-f19d-acf003a0cdc2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249259(v=office.15)
ms:contentKeyID: 48544787
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3258ffcab87b16e4931c9881a8e8d1cd2143262f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468465"
---
# <a name="absoluteposition-property-ado"></a><span data-ttu-id="c1fef-102">AbsolutePosition 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="c1fef-102">AbsolutePosition Property (ADO)</span></span>


<span data-ttu-id="c1fef-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c1fef-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c1fef-104">指示 [Recordset](recordset-object-ado.md) 对象的当前记录的序号位置。</span><span class="sxs-lookup"><span data-stu-id="c1fef-104">Indicates the ordinal position of a [Recordset](recordset-object-ado.md) object's current record.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="c1fef-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="c1fef-105">Settings and Return Values</span></span>

<span data-ttu-id="c1fef-106">设置或返回一个 **Long** 值，该值的范围为 1 到 **Recordset** 对象中的记录数 ([RecordCount](recordcount-property-ado.md))；或返回 [PositionEnum](positionenum.md) 值之一。</span><span class="sxs-lookup"><span data-stu-id="c1fef-106">Sets or returns a **Long** value from 1 to the number of records in the **Recordset** object ([RecordCount](recordcount-property-ado.md)), or returns one of the [PositionEnum](positionenum.md) values.</span></span>

## <a name="remarks"></a><span data-ttu-id="c1fef-107">备注</span><span class="sxs-lookup"><span data-stu-id="c1fef-107">Remarks</span></span>

<span data-ttu-id="c1fef-108">为了设置 **AbsolutePosition** 属性，ADO 要求所使用的 OLE DB 提供程序实现 IRowsetLocate 接口。</span><span class="sxs-lookup"><span data-stu-id="c1fef-108">In order to set the **AbsolutePosition** property, ADO requires that the OLE DB provider you are using implement the IRowsetLocate interface.</span></span>

<span data-ttu-id="c1fef-p101">访问使用只进游标或动态游标打开的 **Recordset** 的 **AbsolutePosition** 属性会引发错误 **adErrFeatureNotAvailable**。对于其他游标类型，只要提供程序支持 IRowsetScroll 接口，就能返回正确的位置。如果提供程序不支持 *IRowsetScroll* 接口，该属性会设置为 **adPosUnknown**。请参阅您的提供程序文档，以确定它是否支持 *IRowsetScroll*。</span><span class="sxs-lookup"><span data-stu-id="c1fef-p101">Accessing the **AbsolutePosition** property of a **Recordset** that was opened with either a forward-only or dynamic cursor raises the error **adErrFeatureNotAvailable**. With other cursor types, the correct position will be returned as long as the provider supports the IRowsetScroll interface. If the provider does not support the *IRowsetScroll* interface, the property is set to **adPosUnknown**. See the documentation for your provider to determine whether it supports *IRowsetScroll*.</span></span>

<span data-ttu-id="c1fef-p102">使用 **AbsolutePosition** 属性，可以根据记录在 **Recordset** 对象中的序号位置移动到记录，或确定当前记录的序号位置。提供程序必须支持相应的功能，此属性才可用。</span><span class="sxs-lookup"><span data-stu-id="c1fef-p102">Use the **AbsolutePosition** property to move to a record based on its ordinal position in the **Recordset** object, or to determine the ordinal position of the current record. The provider must support the appropriate functionality for this property to be available.</span></span>

<span data-ttu-id="c1fef-p103">和 [AbsolutePage](absolutepage-property-ado.md) 属性一样， **AbsolutePosition** 将从 1 开始，当前记录为 **Recordset** 中的第一条记录时，它等于 1。可以通过 **RecordCount** 属性获得 [Recordset](recordcount-property-ado.md) 对象中的记录总数。</span><span class="sxs-lookup"><span data-stu-id="c1fef-p103">Like the [AbsolutePage](absolutepage-property-ado.md) property, **AbsolutePosition** is 1-based and equals 1 when the current record is the first record in the **Recordset**. You can obtain the total number of records in the **Recordset** object from the [RecordCount](recordcount-property-ado.md) property.</span></span>

<span data-ttu-id="c1fef-p104">设置 **AbsolutePosition** 属性时，即使设置为当前缓存中的记录，ADO 也会向缓存中重新加载从指定的记录开始的一组新记录。 [CacheSize](cachesize-property-ado.md) 属性将确定此组的大小。</span><span class="sxs-lookup"><span data-stu-id="c1fef-p104">When you set the **AbsolutePosition** property, even if it is to a record in the current cache, ADO reloads the cache with a new group of records starting with the record you specified. The [CacheSize](cachesize-property-ado.md) property determines the size of this group.</span></span>


> [!NOTE]
> <P><span data-ttu-id="c1fef-p105">[!注释] 不应使用 <STRONG>AbsolutePosition</STRONG> 属性作为代理记录号。当删除位于给定记录之前的记录时，给定记录的位置会发生改变。如果对 <STRONG>Recordset</STRONG> 对象进行了重新查询或重新打开操作，则也不能保证给定的记录仍然具有相同的 <STRONG>AbsolutePosition</STRONG> 。仍然建议采用书签保留和返回到给定位置，而且这是唯一能适用于所有 <STRONG>Recordset</STRONG> 对象类型的定位方法。</span><span class="sxs-lookup"><span data-stu-id="c1fef-p105">You should not use the <STRONG>AbsolutePosition</STRONG> property as a surrogate record number. The position of a given record changes when you delete a preceding record. There is also no assurance that a given record will have the same <STRONG>AbsolutePosition</STRONG> if the <STRONG>Recordset</STRONG> object is requeried or reopened. Bookmarks are still the recommended way of retaining and returning to a given position and are the only way of positioning across all types of <STRONG>Recordset</STRONG> objects.</span></span></P>


