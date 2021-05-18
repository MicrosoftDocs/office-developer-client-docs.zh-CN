---
title: 'RaiseError 宏操作 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 5e29bf64-300a-4094-82ff-664e79782d86
description: RaiseError 操作显示一个弹出窗口，其中包含指定的错误消息。
ms.openlocfilehash: 49e544d2234759709c19052b5540d42e88070849
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408241"
---
# <a name="raiseerror-macro-action-access-custom-web-app"></a>RaiseError 宏操作 (Access 自定义 Web 应用) 

**RaiseError** 操作显示一个弹出窗口，其中包含指定的错误消息。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
> [!NOTE]
> **RaiseError** 操作仅适用于数据宏。 
  
## <a name="setting"></a>设置

**RaiseError** 操作具有以下参数。 
  
|**参数**|**说明**|
|:-----|:-----|
| _Error Description_ <br/> |一个描述错误的字符串表达式。  <br/> |
   
## <a name="remarks"></a>备注

调用 **RaiseError** 操作时，将回滚当前事务中所有操作。 
  

