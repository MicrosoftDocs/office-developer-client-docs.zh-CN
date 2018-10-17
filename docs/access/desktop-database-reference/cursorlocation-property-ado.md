---
title: CursorLocation 属性 (ADO)
TOCTitle: CursorLocation Property (ADO)
ms:assetid: 8a048bd4-ae25-a555-1c07-14364b7e6560
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249606(v=office.15)
ms:contentKeyID: 48546182
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9805b032a0e1a203d2a4057fb74757826a2a47b4
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467324"
---
# <a name="cursorlocation-property-ado"></a><span data-ttu-id="6d08f-102">CursorLocation 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="6d08f-102">CursorLocation Property (ADO)</span></span>


<span data-ttu-id="6d08f-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="6d08f-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="6d08f-104">指示游标服务的位置。</span><span class="sxs-lookup"><span data-stu-id="6d08f-104">Indicates the location of the cursor service.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="6d08f-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="6d08f-105">Settings And Return Values</span></span>

<span data-ttu-id="6d08f-106">设置或返回一个 **Long** 值，该值可以设置为 [CursorLocationEnum](cursorlocationenum.md) 值之一。</span><span class="sxs-lookup"><span data-stu-id="6d08f-106">Sets or returns a **Long** value that can be set to one of the [CursorLocationEnum](cursorlocationenum.md) values.</span></span>

## <a name="remarks"></a><span data-ttu-id="6d08f-107">备注</span><span class="sxs-lookup"><span data-stu-id="6d08f-107">Remarks</span></span>

<span data-ttu-id="6d08f-p101">此属性允许在提供程序可访问的各种游标库间进行选择。通常，可以选择使用客户端游标库或位于服务器上的游标库。</span><span class="sxs-lookup"><span data-stu-id="6d08f-p101">This property allows you to choose between various cursor libraries accessible to the provider. Usually, you can choose between using a client-side cursor library or one that is located on the server.</span></span>

<span data-ttu-id="6d08f-p102">此属性设置仅影响在设置了该属性后建立的连接。更改 **CursorLocation** 属性对现有的连接没有影响。</span><span class="sxs-lookup"><span data-stu-id="6d08f-p102">This property setting affects connections established only after the property has been set. Changing the **CursorLocation** property has no effect on existing connections.</span></span>

<span data-ttu-id="6d08f-p103">[Execute](https://msdn.microsoft.com/library/jj249832\(v=office.15\)) 方法返回的游标将继承此设置。 **Recordset** 对象将从其关联的连接自动继承此设置。</span><span class="sxs-lookup"><span data-stu-id="6d08f-p103">Cursors returned by the [Execute](https://msdn.microsoft.com/library/jj249832\(v=office.15\)) method inherit this setting. **Recordset** objects will automatically inherit this setting from their associated connections.</span></span>

<span data-ttu-id="6d08f-114">此属性在 [Connection](connection-object-ado.md) 或已关闭的 [Recordset](recordset-object-ado.md) 上为可读/写属性，而在打开的 **Recordset** 上为只读属性。</span><span class="sxs-lookup"><span data-stu-id="6d08f-114">This property is read/write on a [Connection](connection-object-ado.md) or a closed [Recordset](recordset-object-ado.md), and read-only on an open **Recordset**.</span></span>

<span data-ttu-id="6d08f-115">**远程数据服务用法**客户端**Recordset**或**Connection**对象上时，**会在 CursorLocation**属性可以仅将设置为**adUseClient**。</span><span class="sxs-lookup"><span data-stu-id="6d08f-115">**Remote Data Service Usage**When used on a client-side **Recordset** or **Connection** object, the **CursorLocation** property can only be set to **adUseClient**.</span></span>
