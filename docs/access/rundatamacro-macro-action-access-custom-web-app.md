---
title: RunDataMacro 宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: f6010ac5-6c08-4c1b-a811-ff81b30ed5f0
description: 您可以使用 RunDataMacro 操作运行独立的数据宏。
ms.openlocfilehash: 55a0ff4c731dc517c5d71aa20d8e46c3b4ff4611
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773595"
---
# <a name="rundatamacro-macro-action-access-custom-web-app"></a>RunDataMacro 宏操作 （访问自定义 web 应用程序）

您可以使用**RunDataMacro**操作运行独立的数据宏。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="setting"></a>设置

**RunDataMacro** 操作具有以下参数。 
  
|**操作参数**|**说明**|
|:-----|:-----|
| _宏名_ <br/> |要运行的数据宏的名称。  <br/> |
   
## <a name="remarks"></a>注释

当您选择要在宏设计器中运行的数据宏时，Access 将确定该数据宏是否需要参数。 如果数据宏需要参数，文本框将显示您可在其中键入参数。
  
当您运行包含 **RunDataMacro** 操作的宏并且该宏到达 **RunDataMacro** 操作时，Access 将运行调用的数据宏。当调用的数据宏完成时，Access 将返回到原始宏并运行下一操作。 
  

