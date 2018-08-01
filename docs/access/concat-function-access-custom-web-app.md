---
title: Concat 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 38ad6365-79df-4342-9b76-ca27b8ab8952
description: 返回 string 类型的值组合两个或多个字符串值的结果。
ms.openlocfilehash: fc0de43e5e42cc1c39ee89cf76058b8039daf279
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773417"
---
# <a name="concat-function-access-custom-web-app"></a>Concat 函数 （访问自定义 web 应用程序）

返回 string 类型的值组合两个或多个字符串值的结果。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

**Concat**(*Value1*， *Value2*，...[*ValueN*]) 
  
**Concat**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
|值  <br/> |要连接到其他值的字符串值。  <br/> |
   
## <a name="remarks"></a>说明

**Concat**采用变量的字符串参数数目，并将它们连接到单个字符串。 至少两个字符串参数是必需的;否则，将引发错误。 
  
所有参数都隐式转换为 string 数据类型，然后连接。
  
## <a name="example"></a>示例

以下表达式可显示联系人的完整名称其中表包含 FirstName、 MiddleInitial 和 LastName 字段。 如果 MiddleInitial 字段为空，组合仅的 FirstName 和 LastName 字段以显示完整的名称。
  
```vb
IIf([MiddleInitial] Is Null,Concat([FirstName]," ",[LastName]),Concat([FirstName]," ",[MiddleInitial]," ",[LastName]))
```


