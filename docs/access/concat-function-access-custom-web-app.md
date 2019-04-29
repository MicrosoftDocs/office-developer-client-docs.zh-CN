---
title: Concat 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 38ad6365-79df-4342-9b76-ca27b8ab8952
description: 返回一个字符串, 表示组合两个或更多字符串值的结果。
ms.openlocfilehash: b8f52c292e64939f9464bc666ecc4bc341580f94
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423270"
---
# <a name="concat-function-access-custom-web-app"></a>Concat 函数 (Access 自定义 web 应用程序)

返回一个字符串, 表示组合两个或更多字符串值的结果。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

**Concat**(*Value1*、 *Value2*、.。。[*ValueN*]) 
  
**Concat**函数包含下列参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
|值  <br/> |要连接到其他值的字符串值。  <br/> |
   
## <a name="remarks"></a>说明

**Concat**采用可变数目的字符串参数, 并将它们连接为单个字符串。 至少需要两个字符串参数。否则, 将引发错误。 
  
所有参数都隐式转换为 string 数据类型, 然后进行连接。
  
## <a name="example"></a>示例

下面的表达式可用于显示表中包含 FirstName、MiddleInitial 和 LastName 字段的人员的完整名称。 如果 "MiddleInitial" 字段为空, 则只会组合 "名字" 和 "姓氏" 字段以显示完整名称。
  
```vb
IIf([MiddleInitial] Is Null,Concat([FirstName]," ",[LastName]),Concat([FirstName]," ",[MiddleInitial]," ",[LastName]))
```


