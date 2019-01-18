---
title: State 属性 (ADO MD)
TOCTitle: State property (ADO MD)
ms:assetid: 4df09f45-9b62-33ce-b4ed-230e41eaac7a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249249(v=office.15)
ms:contentKeyID: 48544744
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 051a9f0cc50ae3a60edb033f6807f72fc0688976
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28702444"
---
# <a name="state-property-ado-md"></a>State 属性 (ADO MD)


**适用于**： Access 2013、 Office 2013

指示单元格集的当前状态。

## <a name="return-values"></a>返回值

返回一个 **Long** 整数值，该值指示 [Cellset](cellset-object-ado-md.md) 对象的当前状况，并且为只读。以下属性值有效： **adStateClosed** (0) 和 **adStateOpen** (1)。

## <a name="remarks"></a>备注

若要使用 [ObjectStateEnum](objectstateenum.md) 常量名称，必须在项目中引用 ADO 类型库。有关更多信息，请参阅 [将 ADO 与 ADO MD 结合使用](using-ado-with-ado-md.md)。

