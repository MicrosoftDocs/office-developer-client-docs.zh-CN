---
title: "Update Resync 属性 \x97 动态 (ADO)"
TOCTitle: Update Resync Property--Dynamic (ADO)
ms:assetid: 0af9cfd2-8042-65c9-cec6-77d2e7a88ad9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248842(v=office.15)
ms:contentKeyID: 48543166
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f4eea391e99202eeb075d73daa1034dff2042e49
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25604419"
---
# <a name="update-resync-property--dynamic-ado"></a><span data-ttu-id="02d30-102">Update Resync 属性  动态 (ADO)</span><span class="sxs-lookup"><span data-stu-id="02d30-102">Update Resync Property--Dynamic (ADO)</span></span>


<span data-ttu-id="02d30-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="02d30-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="02d30-104">指定是否在 [UpdateBatch](updatebatch-method-ado.md) 方法后跟一个隐式 [Resync](resync-method-ado.md) 方法操作，如果是，还要指定该操作的范围。</span><span class="sxs-lookup"><span data-stu-id="02d30-104">Specifies whether the [UpdateBatch](updatebatch-method-ado.md) method is followed by an implicit [Resync](resync-method-ado.md) method operation, and if so, the scope of that operation.</span></span>

<span data-ttu-id="02d30-105"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="02d30-105"><<<<<<< HEAD</span></span>
## <a name="settings-and-return-values"></a><span data-ttu-id="02d30-106">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="02d30-106">Settings and Return Values</span></span>
=======
## <a name="settings-and-return-values"></a><span data-ttu-id="02d30-107">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="02d30-107">Settings and return values</span></span>
>>>>>>> <span data-ttu-id="02d30-108">master</span><span class="sxs-lookup"><span data-stu-id="02d30-108">master</span></span>

<span data-ttu-id="02d30-109">设置或返回一个或多个[ADCPROP\_UPDATERESYNC\_枚举](adcprop-updateresync-enum.md)值。</span><span class="sxs-lookup"><span data-stu-id="02d30-109">Sets or returns one or more of the [ADCPROP\_UPDATERESYNC\_ENUM](adcprop-updateresync-enum.md) values.</span></span>

## <a name="remarks"></a><span data-ttu-id="02d30-110">说明</span><span class="sxs-lookup"><span data-stu-id="02d30-110">Remarks</span></span>

<span data-ttu-id="02d30-111">ADCPROP 值\_UPDATERESYNC\_枚举可以进行组合，不过 adResyncAll 已代表其余值的组合除外。</span><span class="sxs-lookup"><span data-stu-id="02d30-111">The values of ADCPROP\_UPDATERESYNC\_ENUM may be combined, except for adResyncAll which already represents the combination of the rest of the values.</span></span>

<span data-ttu-id="02d30-112">常量 **adResyncConflicts** 会将各个重新同步值作为基础值存储，但不会重写待定的更改。</span><span class="sxs-lookup"><span data-stu-id="02d30-112">The constant **adResyncConflicts** stores the resync values as underlying values, but does not override pending changes.</span></span>

<span data-ttu-id="02d30-113">**Update Resync** 是一个动态属性，会在 [CursorLocation](recordset-object-ado.md) 属性设置为 [adUseClient](properties-collection-ado.md) 时追加到 [Recordset](cursorlocation-property-ado.md) 对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="02d30-113">**Update Resync** is a dynamic property appended to the [Recordset](recordset-object-ado.md) object [Properties](properties-collection-ado.md) collection when the [CursorLocation](cursorlocation-property-ado.md) property is set to **adUseClient**.</span></span>

