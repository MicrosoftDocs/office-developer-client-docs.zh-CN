---
title: RaiseError 宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 5e29bf64-300a-4094-82ff-664e79782d86
description: RaiseError 操作显示包含指定的错误消息的弹出窗口。
ms.openlocfilehash: 1176804106c5cfd9d4bd30f79f47975593089dbc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773590"
---
# <a name="raiseerror-macro-action-access-custom-web-app"></a>RaiseError 宏操作 （访问自定义 web 应用程序）

**RaiseError**操作显示包含指定的错误消息的弹出窗口。 
  
> [!IMPORTANT]
> [!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
> [!NOTE]
> [!注释] **RaiseError** 操作仅适用于数据宏。 
  
## <a name="setting"></a>设置

**RaiseError**操作具有以下参数。 
  
|**参数**|**说明**|
|:-----|:-----|
| _错误说明_ <br/> |一个描述错误的字符串表达式。  <br/> |
   
## <a name="remarks"></a>注释

当调用**RaiseError**操作时，所有当前事务中的操作将被回滚。 
  

