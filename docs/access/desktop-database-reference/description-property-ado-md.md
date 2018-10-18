---
title: Description 属性 (ADO MD)
TOCTitle: Description Property (ADO MD)
ms:assetid: 06d5e1d0-6ed7-fe14-3723-3790e225482a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248816(v=office.15)
ms:contentKeyID: 48543055
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7dd66e0288e20bcf38adefc2fcc30f1856ebf3e6
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25606869"
---
# <a name="description-property-ado-md"></a>Description 属性 (ADO MD)


**适用于**： Access 2013 |Office 2013

返回当前对象的文本说明。

<<<<<<< 标头
## <a name="return-values"></a>返回值
=======
## <a name="return-values"></a>返回值
>>>>>>> master

返回一个 **String** 值，并且该值为只读。

## <a name="remarks"></a>备注

对于 [Member](member-object-ado-md.md) 对象， **Description** 仅适用于度量和公式成员。对于所有其他类型的成员， **Description** 均返回空字符串 ("")。有关各种成员的更多信息，请参阅 [Type](type-property-ado-md.md) 属性。

此属性仅在 **Level** 对象所属的 [Member](level-object-ado-md.md) 对象上受支持。当从 **Position** 对象所属的 [Member](position-object-ado-md.md) 对象引用此属性时，会发生错误。

