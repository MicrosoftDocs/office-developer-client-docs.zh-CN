---
title: 更新 Resync 动态属性 (ADO)
TOCTitle: Update Resync dynamic property (ADO)
ms:assetid: 0af9cfd2-8042-65c9-cec6-77d2e7a88ad9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248842(v=office.15)
ms:contentKeyID: 48543166
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 653291ade258d602d7ec523dcac7e9fe51dd91fb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308342"
---
# <a name="update-resync-dynamic-property-ado"></a><span data-ttu-id="44e40-102">更新 Resync 动态属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="44e40-102">Update Resync dynamic property (ADO)</span></span>


<span data-ttu-id="44e40-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="44e40-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="44e40-104">指定 [UpdateBatch](updatebatch-method-ado.md) 方法后面是否跟随隐式的 [Resync](resync-method-ado.md) 方法操作，如果跟随，则指定该操作的范围。</span><span class="sxs-lookup"><span data-stu-id="44e40-104">Specifies whether the [UpdateBatch](updatebatch-method-ado.md) method is followed by an implicit [Resync](resync-method-ado.md) method operation, and if so, the scope of that operation.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="44e40-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="44e40-105">Settings and return values</span></span>

<span data-ttu-id="44e40-106">设置或返回一个或多个[\_ADCPROP UPDATERESYNC\_枚举](adcprop-updateresync-enum.md)值。</span><span class="sxs-lookup"><span data-stu-id="44e40-106">Sets or returns one or more of the [ADCPROP\_UPDATERESYNC\_ENUM](adcprop-updateresync-enum.md) values.</span></span>

## <a name="remarks"></a><span data-ttu-id="44e40-107">注解</span><span class="sxs-lookup"><span data-stu-id="44e40-107">Remarks</span></span>

<span data-ttu-id="44e40-108">ADCPROP\_UPDATERESYNC\_枚举的值可能会组合在一起, 但已代表其余值的组合的 adResyncAll 除外。</span><span class="sxs-lookup"><span data-stu-id="44e40-108">The values of ADCPROP\_UPDATERESYNC\_ENUM may be combined, except for adResyncAll which already represents the combination of the rest of the values.</span></span>

<span data-ttu-id="44e40-109">常量 **adResyncConflicts** 会将各个重新同步值作为基础值存储，但不会重写待定的更改。</span><span class="sxs-lookup"><span data-stu-id="44e40-109">The constant **adResyncConflicts** stores the resync values as underlying values, but does not override pending changes.</span></span>

<span data-ttu-id="44e40-110">**Update Resync** 是一个动态属性，会在 [CursorLocation](cursorlocation-property-ado.md) 属性设置为 **adUseClient** 时追加到 [Recordset](recordset-object-ado.md) 对象的 [Properties](properties-collection-ado.md) 集合中。</span><span class="sxs-lookup"><span data-stu-id="44e40-110">**Update Resync** is a dynamic property appended to the [Recordset](recordset-object-ado.md) object [Properties](properties-collection-ado.md) collection when the [CursorLocation](cursorlocation-property-ado.md) property is set to **adUseClient**.</span></span>

