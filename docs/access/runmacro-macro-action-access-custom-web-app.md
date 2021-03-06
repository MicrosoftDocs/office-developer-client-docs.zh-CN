---
title: 'RunMacro 宏操作 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 59ba365d-cff5-4126-bc22-4d5a37578aab
description: 可以使用 RunMacro 操作在 UI (运行用户界面) 宏。
ms.openlocfilehash: 98e3b17a6c64fa12ac37e4551d45714c873f5ccb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438440"
---
# <a name="runmacro-macro-action-access-custom-web-app"></a>RunMacro 宏操作 (Access 自定义 Web 应用) 

可以使用 **RunMacro** 操作在 UI 宏中 (用户界面) 用户界面。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="setting"></a>设置

**RunMacro** 操作具有下列参数。 
  
|**操作参数**|**说明**|
|:-----|:-----|
|**宏名** <br/> |要运行的 UI 宏的名称。  <br/> |
   
## <a name="remarks"></a>备注

运行包含 **RunMacro** 操作且到达 **RunMacro** 操作时，Access 将运行调用的 UI 宏。 调用的 UI 宏完成后，Access 将返回到原始 UI 宏并运行下一个操作。 
  

