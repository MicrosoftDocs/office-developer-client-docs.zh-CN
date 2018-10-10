---
title: LockType 属性 (ADO)
TOCTitle: LockType Property (ADO)
ms:assetid: 1d2622dc-6cab-1b7f-98a8-97a41d5c047f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248965(v=office.15)
ms:contentKeyID: 48543589
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6d1740f42fae3485d88a4820081621f7f2483c51
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468165"
---
# <a name="locktype-property-ado"></a><span data-ttu-id="c7bd0-102">LockType 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="c7bd0-102">LockType Property (ADO)</span></span>


<span data-ttu-id="c7bd0-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c7bd0-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c7bd0-104">指示编辑过程中为记录设置的锁定类型。</span><span class="sxs-lookup"><span data-stu-id="c7bd0-104">Indicates the type of locks placed on records during editing.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="c7bd0-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="c7bd0-105">Settings and Return Values</span></span>

<span data-ttu-id="c7bd0-p101">设置或返回一个 [LockTypeEnum](locktypeenum.md) 值。默认值为 **adLockReadOnly** 。</span><span class="sxs-lookup"><span data-stu-id="c7bd0-p101">Sets or returns a [LockTypeEnum](locktypeenum.md) value. The default value is **adLockReadOnly**.</span></span>

## <a name="remarks"></a><span data-ttu-id="c7bd0-108">备注</span><span class="sxs-lookup"><span data-stu-id="c7bd0-108">Remarks</span></span>

<span data-ttu-id="c7bd0-p102">在打开 **Recordset** 前设置 [LockType](recordset-object-ado.md) 属性可指定在打开该记录集时提供程序应使用的锁定类型。读取该属性将返回在打开的 **Recordset** 对象上使用的锁定类型。</span><span class="sxs-lookup"><span data-stu-id="c7bd0-p102">Set the **LockType** property before opening a [Recordset](recordset-object-ado.md) to specify what type of locking the provider should use when opening it. Read the property to return the type of locking in use on an open **Recordset** object.</span></span>

<span data-ttu-id="c7bd0-p103">提供程序可能不支持所有锁定类型。如果某个提供程序不能支持请求的 **LockType** 设置，则将用其他锁定类型替代。若要确定 **Recordset** 对象可用的实际锁定功能，请在 [adUpdate](supports-method-ado.md) 和 **adUpdateBatch** 中使用 **Supports** 方法。</span><span class="sxs-lookup"><span data-stu-id="c7bd0-p103">Providers may not support all lock types. If a provider cannot support the requested **LockType** setting, it will substitute another type of locking. To determine the actual locking functionality available in a **Recordset** object, use the [Supports](supports-method-ado.md) method with **adUpdate** and **adUpdateBatch**.</span></span>

<span data-ttu-id="c7bd0-p104">如果 **CursorLocation** 属性设置为 [adUseClient](cursorlocation-property-ado.md) ，则不支持 **adLockPessimistic** 设置。如果设置不受支持的值，则不会产生错误，因为此时将改用最接近的受支持的 **LockType** 。</span><span class="sxs-lookup"><span data-stu-id="c7bd0-p104">The **adLockPessimistic** setting is not supported if the [CursorLocation](cursorlocation-property-ado.md) property is set to **adUseClient**. If an unsupported value is set, then no error will result; the closest supported **LockType** will be used instead.</span></span>

<span data-ttu-id="c7bd0-116">**Recordset** 关闭时 **LockType** 属性为可读/写属性，而打开时为只读属性。</span><span class="sxs-lookup"><span data-stu-id="c7bd0-116">The **LockType** property is read/write when the **Recordset** is closed and read-only when it is open.</span></span>

<span data-ttu-id="c7bd0-117">**远程数据服务用法**当客户端 Recordset 对象上使用时， **LockType**属性可以仅可设为**adLockBatchOptimistic**。</span><span class="sxs-lookup"><span data-stu-id="c7bd0-117">**Remote Data Service Usage**When used on a client-side Recordset object, the **LockType** property can only be set to **adLockBatchOptimistic**.</span></span>

