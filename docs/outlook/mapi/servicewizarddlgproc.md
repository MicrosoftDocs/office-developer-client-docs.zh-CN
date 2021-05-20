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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432378"
---
# <a name="servicewizarddlgproc"></a>SERVICEWIZARDDLGPROC
 
**适用于**：Outlook 2013 | Outlook 2016 
  
定义由配置文件向导调用的回调函数，以允许服务提供商在显示提供程序的属性表或页面时响应用户事件。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiwz.h  <br/> |
|定义的函数实现方：  <br/> |服务提供程序  <br/> |
|由调用的已定义函数：  <br/> |MAPI 配置文件向导  <br/> |
   
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
  
> [in]"配置文件向导"对话框的窗口句柄。 
    
_wMsgID_
  
> [in]要处理的窗口消息。 除了模式对话框预期的常规窗口消息之外，还可以接收以下消息：
    
WM_CLOSE 
  
> 配置文件向导已完成。 服务提供商应执行所有所需的清理操作，例如取消分配任何动态分配的内存。 
    
WM_COMMAND 
  
> 已选择提供程序的控件之一，或者单击了"下一步"或"后退"按钮。 _wParam_ 参数中的值指示发生了哪些用户事件。 
    
WM_INITDIALOG 
  
> 用户已移动到另一个属性页，必须初始化其对话框。 提供程序应初始化"配置文件向导"已添加到对话框中的控件。 
    
WIZ_QUERYNUMPAGES 
  
> 配置文件向导提示输入提供程序需要显示的页数。 提供程序应返回页数，而不是 TRUE 或 FALSE。 例如，使用以下返回语句指示应显示三个页面：
    
   ```cpp
return (BOOL)3;

   ```

_wParam_
  
> [in]与窗口消息关联的 32 位参数。 可能的值取决于  _wMsgID_ 参数中指定的邮件。 除了模式对话框的常规窗口消息中预期的值之外，还可以接收以下值： 
    
WIZ_NEXT 
  
> 当  _wMsgID_ 包含WM_COMMAND时，用户已单击"下一步 **"** 按钮。 
    
WIZ_PREV 
  
> 当  _wMsgID_ 包含WM_COMMAND时，用户已单击"后退 **"** 按钮。 
    
_lParam_
  
> [in]与窗口消息关联的 32 位参数。 可能的值取决于  _wMsgID_ 参数中指定的邮件。 
    
## <a name="return-value"></a>返回值

基于 **SERVICEWIZARDDLGPROC** 的函数返回的值取决于收到的窗口消息。 尤其要注意邮件的异常WIZ_QUERYNUMPAGES值。 正常返回值为： 
  
TRUE 
  
> 服务提供商已处理收到的窗口消息。 
    
FALSE 
  
> 服务提供商尚未处理收到的窗口消息。
    
## <a name="remarks"></a>备注

当用户从一个属性页移动到另一个属性页时，提供程序负责隐藏旧页面的控件，并显示下一页或上一页的控件。 当用户单击"下一步"按钮时，将调用基于 **SERVICEWIZARDDLGPROC** 的函数，WM_COMMAND消息，WIZ_NEXT _wParam_ 参数中调用。 以下步骤介绍在用户单击"下一步"到呈现第一个提供程序的配置页面之间发生的情况。 
  
1. "配置文件向导"隐藏窗口上的任何控件。 
    
2. "配置文件向导"将提供程序的隐藏控件添加到页面。 
    
3. 配置文件向导调用 **SERVICEWIZARDDLGPROC**，发送WM_INITDIALOG消息，以便提供程序可以初始化控件。 
    
4. 配置文件向导调用 **SERVICEWIZARDDLGPROC，** 发送WIZ_QUERYNUMPAGES消息。 提供程序返回要显示的页数。 
    
5. 配置文件向导调用 **SERVICEWIZARDDLGPROC，WM_COMMAND**  _wParam_ 参数设置为 WIZ_NEXT 或 WIZ_PREV。 此时，提供程序返回 FALSE {error} 或显示其控件并返回 TRUE {success}。 如果"配置文件向导"ID_NEXT，将显示提供程序的第一页。 如果ID_PREV，则显示最后一页。 
    
6. 配置文件向导调用提供程序的 **SERVICEWIZARDDLGPROC** 函数，发送  _wParam_ 参数设置为 WIZ_NEXT 或 WIZ_PREV (的 WM_COMMAND 消息，具体取决于用户单击) 的按钮。 提供程序负责显示或隐藏其控件，以及将数据写入传递到配置文件向导的 **IMAPIProp，** 以逐步完成其页面序列。 如果成功显示下一页或上一页，提供程序应返回 TRUE;如果下一页和上一页都未显示，则返回 FALSE。 提供程序需要了解何时在页面序列之外单步执行，并且通过隐藏其控件和将数据写入配置文件来做出相应的响应。 
    
7. 如果用户的步骤超出提供程序的页面范围，则配置文件向导将从对话框中删除提供程序的隐藏控件，并调用下一个提供程序，或者显示其下一页（如果这是最后一个提供程序）。 
    

