---
title: Name 属性 (ADO MD)
TOCTitle: Name property (ADO MD)
ms:assetid: 31ea6dad-c464-3af7-4b7a-086900656c2c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249093(v=office.15)
ms:contentKeyID: 48544065
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 971a528c0efe97626f08ff94490e8aee25230f60
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25926533"
---
# <a name="name-property-ado-md"></a>Name 属性 (ADO MD)


**适用于**： Access 2013、 Office 2013

指示对象的名称。

## <a name="return-values"></a>返回值

返回一个 **String** 值，并且该值为只读。

## <a name="remarks"></a>备注

可按序号引用来检索对象的 **Name** 属性，此后就可按名称直接引用该对象。例如，如果 cdf.CubeDefs(0).Name 得到"Bobs Video Store"，则可按 cdf.CubeDefs("Bobs Video Store") 形式引用此 [CubeDef](cubedef-object-ado-md.md)。

