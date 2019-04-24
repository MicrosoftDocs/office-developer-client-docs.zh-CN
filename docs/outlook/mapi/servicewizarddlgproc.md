---
title: SERVICEWIZARDDLGPROC
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SERVICEWIZARDDLGPROC
api_type:
- COM
ms.assetid: 3e2d5190-e67a-470d-8177-0f0ba20c7b82
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e43a1d7c57668ba930b4c4af7194bd298971e6ba
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356411"
---
# <a name="servicewizarddlgproc"></a>SERVICEWIZARDDLGPROC
 
**适用于**：Outlook 2013 | Outlook 2016 
  
定义由配置文件向导调用的回调函数, 以允许服务提供程序在显示提供程序的属性表或页面时对用户事件做出响应。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiwz  <br/> |
|定义的函数实现者:  <br/> |服务提供程序  <br/> |
|定义的函数调用者:  <br/> |MAPI 配置文件向导  <br/> |
   
```cpp
BOOL SERVICEWIZARDDLGPROC(
  HWND hDlg,
  UINT wMsgID,
  WPARAM wParam,
  LPARAM lParam
);
```

## <a name="parameters"></a>参数

_hDlg_
  
> 实时"配置文件向导" 对话框的窗口句柄。 
    
_wMsgID_
  
> 实时要处理的窗口消息。 除了模式对话框预期的常规窗口消息之外, 还可以接收以下消息:
    
WM_CLOSE 
  
> 配置文件向导已完成。 服务提供程序应执行所有必要的清理操作, 如释放任何动态分配的内存。 
    
WM_COMMAND 
  
> 已选择某个提供程序的控件, 或单击了 "**下一步**" 或 "**后退**" 按钮。 _wParam_参数中的值指示发生了哪些用户事件。 
    
WM_INITDIALOG 
  
> 用户已移动到另一个属性页, 该属性页必须为其初始化对话框。 提供程序应初始化 "配置文件向导" 已添加到对话框中的控件。 
    
WIZ_QUERYNUMPAGES 
  
> [! 注意] 配置文件向导提示输入提供程序需要显示的页面数。 提供程序应返回页面的数目, 而不是 TRUE 或 FALSE。 例如, 使用以下 return 语句指示应显示三个页面:
    
   ```cpp
return (BOOL)3;

   ```

_wParam_
  
> 实时与窗口消息相关联的32位参数。 可能的值取决于在_wMsgID_参数中指定的消息。 除了针对模式对话框的常规窗口消息的预期值外, 还可以接收以下值: 
    
WIZ_NEXT 
  
> 当_wMsgID_包含 WM_COMMAND 时, 用户单击了 "**下一步**" 按钮。 
    
WIZ_PREV 
  
> 当_wMsgID_包含 WM_COMMAND 时, 用户已单击 "**后退**" 按钮。 
    
_lParam_
  
> 实时与窗口消息相关联的32位参数。 可能的值取决于在_wMsgID_参数中指定的消息。 
    
## <a name="return-value"></a>返回值

基于**SERVICEWIZARDDLGPROC**的函数返回的值取决于收到的窗口消息。 具体来说, 请注意 WIZ_QUERYNUMPAGES 消息的异常返回值。 正常的返回值为: 
  
TRUE 
  
> 服务提供程序已处理收到的窗口消息。 
    
FALSE 
  
> 服务提供程序尚未处理收到的窗口消息。
    
## <a name="remarks"></a>注解

当用户从一个属性页移到另一个时, 提供程序负责隐藏旧页面的控件, 并显示下一页或上一页的控件。 当用户单击 "**下一步**" 按钮时, 将在_wParam_参数中使用 WM_COMMAND 消息和 WIZ_NEXT 调用基于**SERVICEWIZARDDLGPROC**的函数。 以下步骤描述了用户单击 "**下一步**" 和第一个提供程序的配置页面呈现时间之间发生的情况。 
  
1. "配置文件向导" 将隐藏窗口上的所有控件。 
    
2. "配置文件向导" 将提供程序的隐藏控件添加到页面中。 
    
3. [! 注意] 配置文件向导调用**SERVICEWIZARDDLGPROC**, 发送 WM_INITDIALOG 消息, 以便提供程序可以初始化控件。 
    
4. 配置文件向导调用**SERVICEWIZARDDLGPROC**, 同时发送 WIZ_QUERYNUMPAGES 消息。 提供程序返回要显示的页面的数量。 
    
5. 配置文件向导调用**SERVICEWIZARDDLGPROC**, 并将 WM_COMMAND 消息的_wParam_参数设置为 WIZ_NEXT 或 WIZ_PREV。 在这种情况下, 提供程序要么返回 FALSE {error}, 要么显示它的控件, 并返回 TRUE {success}。 如果配置文件向导在 ID_NEXT 中传递, 则显示提供程序的第一个页面。 如果传入 ID_PREV, 则显示最后一页。 
    
6. 配置文件向导调用提供程序的**SERVICEWIZARDDLGPROC**函数, 并将_wParam_参数设置为 WIZ_NEXT 或 WIZ_PREV (具体取决于用户单击的按钮) 的 WM_COMMAND 消息。 提供程序负责显示或隐藏其控件, 并将其数据写入到传递给配置文件向导的**IMAPIProp**中, 以遍历其页面序列。 如果成功显示下一个或上一个页面, 提供程序应返回 TRUE; 如果下一个或上一个页面都不能显示, 则返回 FALSE。 提供程序需要知道何时在其页面序列之外进行跟踪, 并通过隐藏其控件并将其数据写入配置文件进行适当的响应。 
    
7. 如果用户步骤不在提供程序的页面范围之外, 则配置文件向导会从对话框中删除提供程序的隐藏控件, 并调用下一个提供程序, 如果是最后一个提供程序, 则将显示其下一个页面。 
    

