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
ms.openlocfilehash: 2505f555fd8867fdc24a14f523a74b6f478a3e70
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774844"
---
# <a name="dtblbutton"></a>DTBLBUTTON

  
  
**适用于**： Outlook 
  
包含显示表中生成的对话框的按钮控件的信息。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的宏：  <br/> |[SizedDtblButton](sizeddtblbutton.md) <br/> |
   
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
  
> 在按钮上显示的字符字符串的内存中的位置。
    
 **ulFlags**
  
> 用于指定所指的**ulbLpszLabel**成员标签的格式的标志位掩码。 可以设置以下标记： 
    
MAPI_UNICODE 
  
> 标签为 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，标签为 ANSI 格式。
    
 **ulPRControl**
  
> 属性标记 PT_OBJECT 实现[IMAPIControl](imapicontroliunknown.md)接口的类型的属性。 当单击按钮时，MAPI 调用显示表[IMAPIProp](imapipropiunknown.md)实现，以检索此属性的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法。 
    
## <a name="remarks"></a>说明

**DTBLBUTTON**结构描述一个按钮控件，单击时，允许用户开始操作。 通常情况下，单击按钮会将显示一个模式对话框或要调用的编程任务。 服务提供商可以实现通过一个按钮控件的任何内容。 如果按钮应该执行任务基于其他控件的值，这些控件必须设置 DT_SET_IMMEDIATE 标志。 
  
**UlbLpszLabel**成员是在按钮上显示的字符字符串的内存中的位置。 服务提供商可以添加 & 字符 (&amp;) 以指示在按钮标签 Windows 加速键。 按加速键与单击的按钮的效果相同。 
  
**UlPRControl**成员介绍对象属性，当用**IMAPIProp::OpenProperty**方法打开，返回指向 control 对象的指针。 实现支持**IMAPIControl**接口的控件对象是一种方法扩展 MAPI 功能集，并定义操作或任务的单击按钮时，发生此事件。 **IMAPIControl**提供操作按钮的两种方法： [GetState](imapicontrol-getstate.md)禁用或启用按钮和[激活](imapicontrol-activate.md)处理按钮单击。 
  
显示表的概述，请参阅[显示表](display-tables.md)。 有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)


[MAPI 结构](mapi-structures.md)

