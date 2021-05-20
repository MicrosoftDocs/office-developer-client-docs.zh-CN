---
title: 'StopMacro 宏操作 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: af28534b-6f0d-43ee-ae89-ee2f85da1af1
description: 可以使用 StopMacro 操作停止当前运行的宏。
ms.openlocfilehash: 8b80422a297647d556fb4b20cc15fb93e8853466
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429493"
---
# <a name="stopmacro-macro-action-access-custom-web-app"></a>StopMacro 宏操作 (Access 自定义 Web 应用) 

可以使用 **StopMacro** 操作停止当前运行的宏。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="setting"></a>设置

**StopMacro** 操作没有任何参数。 
  
## <a name="remarks"></a>备注

当条件需要停止宏时，通常使用此操作。 例如，您可能在 UI (用户界面) 打开一个视图，该视图显示在当前视图中输入的日期的每日订单总数。 可以使用条件表达式确保对话框中的"订单日期"控件包含有效日期。 如果没有 **，MessageBox** 操作可以显示错误消息， **并且 StopMacro** 操作可以停止 UI 宏。 
  

