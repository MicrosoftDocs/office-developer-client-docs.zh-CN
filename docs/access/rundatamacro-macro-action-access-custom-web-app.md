---
title: 'RunDataMacro 宏操作 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: f6010ac5-6c08-4c1b-a811-ff81b30ed5f0
description: 可以使用 RunDataMacro 操作运行独立数据宏。
ms.openlocfilehash: 68c0e5a3837039bdab1165e686adb3bdf2a5b6f8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439343"
---
# <a name="rundatamacro-macro-action-access-custom-web-app"></a>RunDataMacro 宏操作 (Access 自定义 Web 应用) 

可以使用 **RunDataMacro** 操作运行独立数据宏。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="setting"></a>设置

**RunDataMacro** 操作具有以下参数。 
  
|**操作参数**|**说明**|
|:-----|:-----|
| _宏名_ <br/> |要运行的数据宏的名称。  <br/> |
   
## <a name="remarks"></a>备注

当您选择要在宏设计器中运行的数据宏时，Access 将确定该数据宏是否需要参数。 如果数据宏需要参数，则会显示文本框，您可以在其中键入参数。
  
当您运行包含 **RunDataMacro** 操作的宏并且该宏到达 **RunDataMacro** 操作时，Access 将运行调用的数据宏。当调用的数据宏完成时，Access 将返回到原始宏并运行下一操作。 
  

