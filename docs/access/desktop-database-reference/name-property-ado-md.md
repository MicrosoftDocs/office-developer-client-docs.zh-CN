---
title: Name 属性 (ADO MD)
TOCTitle: Name Property (ADO MD)
ms:assetid: 31ea6dad-c464-3af7-4b7a-086900656c2c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249093(v=office.15)
ms:contentKeyID: 48544065
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0cc7a89e0d6b9cdaed2c54d3269b61280ce3306c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466316"
---
# <a name="name-property-ado-md"></a>Name 属性 (ADO MD)


**适用于**： Access 2013 |Office 2013

指示对象的名称。

## <a name="return-values"></a>返回值

返回一个 **String** 值，并且该值为只读。

## <a name="remarks"></a>备注

可按序号引用来检索对象的 **Name** 属性，此后就可按名称直接引用该对象。例如，如果 cdf.CubeDefs(0).Name 得到"Bobs Video Store"，则可按 cdf.CubeDefs("Bobs Video Store") 形式引用此 [CubeDef](cubedef-object-ado-md.md)。

