---
title: DTBLBUTTON
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLBUTTON
api_type:
- COM
ms.assetid: 6058c78b-05d4-45a3-988c-1fbf8322125e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a8fa683fecd59ec813fee0c15d5b4f08084c645d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412784"
---
# <a name="dtblbutton"></a>DTBLBUTTON

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含根据显示表生成的对话框的按钮控件的相关信息。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关宏:  <br/> |[SizedDtblButton](sizeddtblbutton.md) <br/> |
   
```cpp
typedef struct _DTBLBUTTON
{
  ULONG ulbLpszLabel;
  ULONG ulFlags;
  ULONG ulPRControl;
} DTBLBUTTON, FAR *LPDTBLBUTTON;

```

## <a name="members"></a>Members

 **ulbLpszLabel**
  
> 按钮上显示的字符字符串在内存中的位置。
    
 **ulFlags**
  
> 标志的位掩码, 用于指定**ulbLpszLabel**成员指向的标签的格式。 可以设置以下标志: 
    
MAPI_UNICODE 
  
> 标签采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则标签将采用 ANSI 格式。
    
 **ulPRControl**
  
> 实现[IMAPIControl](imapicontroliunknown.md)接口的类型为 PT_OBJECT 的属性的属性标记。 单击该按钮时, MAPI 将为显示表的[IMAPIProp](imapipropiunknown.md)实现调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法来检索此属性。 
    
## <a name="remarks"></a>说明

**DTBLBUTTON**结构描述一个按钮, 单击该控件时, 用户可以开始操作。 通常情况下, 单击按钮会导致显示模式对话框或调用编程任务。 服务提供程序可以通过按钮控件实现任何内容。 如果按钮应基于其他控件的值执行任务, 则这些控件必须已设置 DT_SET_IMMEDIATE 标志。 
  
**ulbLpszLabel**成员是显示在按钮上的字符字符串在内存中的位置。 服务提供程序可以添加一个与号&amp;字符 (), 以指示按钮标签中的 Windows 加速器。 按加速键与单击按钮具有相同的效果。 
  
**ulPRControl**成员描述了一个对象属性, 该属性在使用**IMAPIProp:: OpenProperty**方法打开时, 返回一个指向 control 对象的指针。 实现支持**IMAPIControl**接口的 control 对象是一种扩展 MAPI 功能集和定义单击按钮时发生的操作或任务的方法。 **IMAPIControl**提供了两种操作按钮的方法: [GetState](imapicontrol-getstate.md)可禁用或启用按钮并[激活](imapicontrol-activate.md)以处理按钮单击。 
  
有关显示表的概述, 请参阅[显示表](display-tables.md)。 有关如何实现显示表的信息, 请参阅[实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)


[MAPI 结构](mapi-structures.md)

