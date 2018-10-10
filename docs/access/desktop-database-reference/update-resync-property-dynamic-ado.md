---
title: "Update Resync 属性 \x97 动态 (ADO)"
TOCTitle: Update Resync Property--Dynamic (ADO)
ms:assetid: 0af9cfd2-8042-65c9-cec6-77d2e7a88ad9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248842(v=office.15)
ms:contentKeyID: 48543166
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 16600f22084718a6b32656ebfc56d6a9be06c676
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467088"
---
# <a name="update-resync-property--dynamic-ado"></a><span data-ttu-id="1b48f-102">Update Resync 属性  动态 (ADO)</span><span class="sxs-lookup"><span data-stu-id="1b48f-102">Update Resync Property--Dynamic (ADO)</span></span>


<span data-ttu-id="1b48f-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="1b48f-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="1b48f-104">指定是否在 [UpdateBatch](updatebatch-method-ado.md) 方法后跟一个隐式 [Resync](resync-method-ado.md) 方法操作，如果是，还要指定该操作的范围。</span><span class="sxs-lookup"><span data-stu-id="1b48f-104">Specifies whether the [UpdateBatch](updatebatch-method-ado.md) method is followed by an implicit [Resync](resync-method-ado.md) method operation, and if so, the scope of that operation.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="1b48f-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="1b48f-105">Settings and Return Values</span></span>

<span data-ttu-id="1b48f-106">设置或返回一个或多个[ADCPROP\_UPDATERESYNC\_枚举](adcprop-updateresync-enum.md)值。</span><span class="sxs-lookup"><span data-stu-id="1b48f-106">Sets or returns one or more of the [ADCPROP\_UPDATERESYNC\_ENUM](adcprop-updateresync-enum.md) values.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b48f-107">说明</span><span class="sxs-lookup"><span data-stu-id="1b48f-107">Remarks</span></span>

<span data-ttu-id="1b48f-108">ADCPROP 值\_UPDATERESYNC\_枚举可以进行组合，不过 adResyncAll 已代表其余值的组合除外。</span><span class="sxs-lookup"><span data-stu-id="1b48f-108">The values of ADCPROP\_UPDATERESYNC\_ENUM may be combined, except for adResyncAll which already represents the combination of the rest of the values.</span></span>

<span data-ttu-id="1b48f-109">常量 **adResyncConflicts** 会将各个重新同步值作为基础值存储，但不会重写待定的更改。</span><span class="sxs-lookup"><span data-stu-id="1b48f-109">The constant **adResyncConflicts** stores the resync values as underlying values, but does not override pending changes.</span></span>

<span data-ttu-id="1b48f-110">**Update Resync** 是一个动态属性，会在 [CursorLocation](recordset-object-ado.md) 属性设置为 [adUseClient](properties-collection-ado.md) 时追加到 [Recordset](cursorlocation-property-ado.md) 对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="1b48f-110">**Update Resync** is a dynamic property appended to the [Recordset](recordset-object-ado.md) object [Properties](properties-collection-ado.md) collection when the [CursorLocation](cursorlocation-property-ado.md) property is set to **adUseClient**.</span></span>

