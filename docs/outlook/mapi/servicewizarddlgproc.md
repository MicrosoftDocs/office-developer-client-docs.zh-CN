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
ms.openlocfilehash: fdd5d01b96c9ea756ee64f113ccb5119a9693668
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594465"
---
# <a name="servicewizarddlgproc"></a>SERVICEWIZARDDLGPROC
 
**适用于**： Outlook 2013 |Outlook 2016 
  
定义由配置文件向导以允许服务提供程序响应用户事件提供程序的属性表或页面显示时调用的回调函数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiwz.h  <br/> |
|通过实施定义的函数：  <br/> |服务提供商  <br/> |
|定义的函数调用：  <br/> |MAPI 配置文件向导  <br/> |
   
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
  
> [in]配置文件向导对话框窗口句柄。 
    
_wMsgID_
  
> [in]要处理的窗口消息。 除了所需的一个模式对话框的正则窗口消息，就会收到以下消息：
    
WM_CLOSE 
  
> 配置文件向导已完成。 服务提供商办所有所需的清理，如取消任何动态分配分配内存。 
    
WM_COMMAND 
  
> 一个提供程序的控件已被选中，或单击**下一步**或**返回**按钮。 _WParam_参数中的值指示其这些用户事件发生。 
    
WM_INITDIALOG 
  
> 用户已移动到另一个属性页上，必须为其初始化的对话框。 提供程序应初始化配置文件向导已添加到对话框中的控件。 
    
WIZ_QUERYNUMPAGES 
  
> 配置文件向导为提示提供程序需要显示的页面的数量。 提供程序应返回的而不是 TRUE 或 FALSE 的页数。 例如，使用以下返回语句以指明应显示三个页面：
    
   ```cpp
return (BOOL)3;

   ```

_wParam_
  
> [in]与窗口消息关联的 32 位参数。 可能的值取决于_wMsgID_参数中指定的消息。 除了能够为一个模式对话框的正则窗口消息的值，就会收到以下值： 
    
WIZ_NEXT 
  
> 当_wMsgID_包含 WM_COMMAND 时，用户单击**下一步**按钮。 
    
WIZ_PREV 
  
> 当_wMsgID_包含 WM_COMMAND 时，用户单击**后退**按钮。 
    
_lParam_
  
> [in]与窗口消息关联的 32 位参数。 可能的值取决于_wMsgID_参数中指定的消息。 
    
## <a name="return-value"></a>返回值

取决于所接收的窗口消息**SERVICEWIZARDDLGPROC**基于函数返回的值。 特别注意特殊的返回值为 WIZ_QUERYNUMPAGES 消息。 普通的返回值为： 
  
TRUE 
  
> 服务提供商已处理的收到的窗口消息。 
    
FALSE 
  
> 服务提供商尚未处理的收到的窗口消息。
    
## <a name="remarks"></a>注解

当用户从一个属性页面移动到另一个时，提供程序负责为隐藏旧页上的控件和显示下一页或上一页页上的控件。 当用户单击**下一步**按钮时， **SERVICEWIZARDDLGPROC**基于函数使用的 WM_COMMAND 消息和 WIZ_NEXT 调用_wParam_参数中。 下面的步骤介绍之间用户单击**下一步**和第一个提供程序的配置页面呈现时间时发生的情形。 
  
1. 配置文件向导隐藏在窗口中的任何控件。 
    
2. 配置文件向导将提供程序的隐藏的控件添加到页。 
    
3. 配置文件向导调用**SERVICEWIZARDDLGPROC**，发送 WM_INITDIALOG 邮件，以便提供程序可以初始化控件。 
    
4. 配置文件向导调用**SERVICEWIZARDDLGPROC**，发送 WIZ_QUERYNUMPAGES 消息。 提供程序返回要显示的页面的数量。 
    
5. 配置文件向导调用**SERVICEWIZARDDLGPROC**， _wParam_参数设置为 WIZ_NEXT 或 WIZ_PREV 发送 WM_COMMAND 消息。 此时，提供程序是返回 FALSE {错误} 或显示其控件并返回 TRUE {成功}。 如果 ID_NEXT 传入配置文件向导，将显示提供程序的第一页。 如果传入 ID_PREV，将显示的最后一页。 
    
6. 配置文件向导调用提供程序的**SERVICEWIZARDDLGPROC**函数，WM_COMMAND 消息发送带有_wParam_参数设置为 WIZ_NEXT 或 WIZ_PREV （具体取决于哪个按钮用户单击）。 提供程序负责为显示或隐藏及其控件并且其数据写入**IMAPIProp**传递给配置文件向导以通过其序列页面的步骤。 如果已成功显示下一页或上一页页上，并且无法显示 FALSE 如果既未下一步，也不是以前页上，提供程序应返回 TRUE。 提供程序需要注意的逐步之外的页面，其序列时并通过隐藏及其控件并将其数据写到配置文件的相应做出响应。 
    
7. 如果用户步骤的页面的提供程序的范围之外，配置文件向导从对话框中删除提供程序的隐藏的控件和调用下一个提供程序或显示其下一页上，如果这正印证了最后的提供程序。 
    

