---
title: SetReturnVar 宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 57965c84-7a52-4d7c-9c7f-be3d4570576d
description: SetReturnVar 操作创建返回变量，并将其设置为特定值。
ms.openlocfilehash: d0638c8f1e3b184a7c685ad8649c8923bdfd8f50
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773627"
---
# <a name="setreturnvar-macro-action-access-custom-web-app"></a>SetReturnVar 宏操作 （访问自定义 web 应用程序）

**SetReturnVar**操作创建返回变量，并将其设置为特定值。 
  
> [!IMPORTANT]
> [!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
> [!NOTE]
> **SetReturnVar**操作仅适用于数据宏。 
  
## <a name="setting"></a>设置

**SetReturnVar**操作具有下列参数。 
  
|**参数名称**|**必需**|**说明**|
|:-----|:-----|:-----|
| _名称_ <br/> |是  <br/> |一个用于指定变量名称的字符串。  <br/> |
| _Expression_ <br/> |是  <br/> |一个表达式，用于设置为临时变量的值。 不在表达式前面放等号 （=）。 您可以单击**生成**按钮以使用**表达式生成器**设置此参数。  <br/> |
   
## <a name="remarks"></a>备注

**SetReturnVar**操作用于创建**ReturnVar**，这是可供使用**RunDataMacro**操作调用的数据宏的宏的变量。 
  
**ReturnVar**创建**SetReturnVar**操作后，调用宏可以使用它在表达式中。 例如，如果您创建名为**UpdateSuccess** **ReturnVar** ，您可以使用该变量使用以下语法：
  
`=[ReturnVars]![UpdateSuccess]`

**SetReturnVar**操作可仅在命名的数据宏。 不适用于数据宏附加到的数据宏事件。 
  

