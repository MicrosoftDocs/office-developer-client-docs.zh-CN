---
title: StopMacro 宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: af28534b-6f0d-43ee-ae89-ee2f85da1af1
description: 您可以使用 StopMacro 操作停止当前正在运行的宏。
ms.openlocfilehash: 54501b65eb1847287e810ae43742a2e6e5384264
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773606"
---
# <a name="stopmacro-macro-action-access-custom-web-app"></a>StopMacro 宏操作 （访问自定义 web 应用程序）

您可以使用**StopMacro**操作停止当前正在运行的宏。 
  
> [!IMPORTANT]
> [!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="setting"></a>设置

**StopMacro**操作不具有任何参数。 
  
## <a name="remarks"></a>说明

通常，当条件进行所需停止宏，可使用此操作。 例如，您可以创建一个用户界面 (UI) 宏的打开视图显示每日的顺序总计的当前视图中输入的日期。 您可以使用的条件表达式以确保对话框上的订单日期控件包含有效的日期。 如果没有， **MessageBox**操作可以显示一条错误消息和**StopMacro**操作可以停止 UI 宏。 
  

