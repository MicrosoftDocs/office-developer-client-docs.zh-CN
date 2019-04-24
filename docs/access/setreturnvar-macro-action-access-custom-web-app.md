---
title: SetReturnVar 宏操作 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 57965c84-7a52-4d7c-9c7f-be3d4570576d
description: SetReturnVar 操作将创建一个返回变量并将其设置为特定值。
ms.openlocfilehash: 29445f5021bed99fe45cee1d34457f1f91ca417d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310941"
---
# <a name="setreturnvar-macro-action-access-custom-web-app"></a>SetReturnVar 宏操作 (Access 自定义 web 应用程序)

**SetReturnVar**操作将创建一个返回变量并将其设置为特定值。 
  
> [!IMPORTANT]
> [!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
> [!NOTE]
> **SetReturnVar**操作仅适用于数据宏。 
  
## <a name="setting"></a>Setting

**SetReturnVar**操作具有下列参数。 
  
|**参数名称**|**必需**|**说明**|
|:-----|:-----|:-----|
| _名称_ <br/> |是  <br/> |一个用于指定变量名称的字符串。  <br/> |
| _Expression_ <br/> |是  <br/> |一个用于设置该临时变量的值的表达式。 该表达式不能以等号 (=) 开头。 可以单击 "**生成**" 按钮以使用**表达式生成器**设置此参数。  <br/> |
   
## <a name="remarks"></a>注解

**SetReturnVar**操作用于创建**ReturnVar**, 它是一个变量, 可供使用**RunDataMacro**操作调用数据宏的宏使用。 
  
在**SetReturnVar**操作创建**ReturnVar**后, 调用宏可以在表达式中使用它。 例如, 如果您创建了一个名为**UpdateSuccess**的**ReturnVar** , 则可以使用以下语法来使用变量:
  
`=[ReturnVars]![UpdateSuccess]`

**SetReturnVar**操作只能在已命名的数据宏中使用。 它在附加到数据宏事件的数据宏中不可用。 
  

