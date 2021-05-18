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
  
包含有关从显示表构建的对话框的按钮控件的信息。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关宏：  <br/> |[SizedDtblButton](sizeddtblbutton.md) <br/> |
   
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
  
> 用于指定 **ulbLpszLabel** 成员指向的标签格式的标志的位掩码。 可以设置以下标志： 
    
MAPI_UNICODE 
  
> 标签采用 Unicode 格式。 如果未MAPI_UNICODE，则标签采用 ANSI 格式。
    
 **ulPRControl**
  
> 实现 [IMAPIControl](imapicontroliunknown.md) 接口PT_OBJECT类型的属性的属性标记。 单击该按钮时，MAPI 将调用显示表的[IMAPIProp 实现中的 IMAPIProp：：OpenProperty](imapiprop-openproperty.md)方法以检索此属性。 [](imapipropiunknown.md) 
    
## <a name="remarks"></a>备注

**DTBLBUTTON** 结构描述按钮控件，单击该控件时，用户可以开始操作。 通常，单击某个按钮会导致显示模式对话框或调用编程任务。 服务提供程序可以通过按钮控件实现任何内容。 如果按钮应基于其他控件的值执行任务，则这些控件必须已设置DT_SET_IMMEDIATE标志。 
  
**ulbLpszLabel** 成员是按钮上显示的字符字符串在内存中的位置。 服务提供商可以添加与号字符 () 按钮标签Windows &amp; 加速键。 按加速键的效果与单击按钮的效果相同。 
  
**ulPRControl** 成员描述一个对象属性，当使用 **IMAPIProp：：OpenProperty** 方法打开该属性时，将返回一个指向控件对象的指针。 实现支持 **IMAPIControl** 接口的控件对象是扩展 MAPI 功能集并定义单击按钮时发生的操作或任务的一种方式。 **IMAPIControl** 提供了两种操作按钮的方法：用于禁用或启用按钮的 [GetState](imapicontrol-getstate.md) 和 [用于](imapicontrol-activate.md) 处理按钮单击的激活。 
  
有关显示表的概述，请参阅显示 [表](display-tables.md)。 若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)


[MAPI 结构](mapi-structures.md)

