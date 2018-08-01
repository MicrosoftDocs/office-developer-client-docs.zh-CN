---
title: RunMacro 宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 59ba365d-cff5-4126-bc22-4d5a37578aab
description: 您可以使用 RunMacro 操作运行用户界面 (UI) 宏。
ms.openlocfilehash: 68a59e246c0af8385a17aedcf3da771c720f8fd7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773600"
---
# <a name="runmacro-macro-action-access-custom-web-app"></a>RunMacro 宏操作 （访问自定义 web 应用程序）

您可以使用**RunMacro**操作运行用户界面 (UI) 宏。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="setting"></a>设置

**RunMacro** 操作具有下列参数。 
  
|**操作参数**|**说明**|
|:-----|:-----|
|**宏名** <br/> |要运行的 UI 宏的名称。  <br/> |
   
## <a name="remarks"></a>说明

当您运行的 UI 宏包含**RunMacro**操作，并会在到达**RunMacro**操作时，Access 将运行该呼叫的 UI 宏。 在完成呼叫的 UI 宏后，Access 将返回到原来的 UI 宏并运行的下一个操作。 
  

