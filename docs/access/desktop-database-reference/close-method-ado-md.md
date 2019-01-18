---
title: Close 方法 (ADO MD)
TOCTitle: Close method (ADO MD)
ms:assetid: 683788b0-0a96-a165-6b49-8d7036850756
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249406(v=office.15)
ms:contentKeyID: 48545382
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 609069d04124146f311166e3ae56d8d6a793675b
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28709829"
---
# <a name="close-method-ado-md"></a>Close 方法 (ADO MD)


**适用于**： Access 2013、 Office 2013

关闭打开的单元格集。

## <a name="syntax"></a>语法

*单元格集*。关闭

## <a name="remarks"></a>说明

使用 **Close** 方法关闭 [Cellset](cellset-object-ado-md.md) 对象会释放关联的数据，包括任何相关的 [Cell](cell-object-ado-md.md)、[Axis](axis-object-ado-md.md)、[Position](position-object-ado-md.md) 或 [Member](member-object-ado-md.md) 对象中的数据。关闭 **Cellset** 不会将其从内存中删除；您可以更改其属性设置，以便以后再打开它。若要从内存中完全消除对象，请将对象变量设置为 **Nothing** 。

您可在以后使用相同的源字符串或其他源字符串调用 [Open](open-method-ado-md.md) 方法，以重新打开 **Cellset** 。在 **Cellset** 对象关闭后，检索或调用引用基础数据或元数据的任何属性或方法都会生成错误。

