---
title: HrOpenABEntryWithSupport
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: eaa988ea-aee1-4066-8c78-2b6c28def5e0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b8574264bdb470906cc097cec56b39a943937d11
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32347759"
---
# <a name="hropenabentrywithsupport"></a>HrOpenABEntryWithSupport

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
请勿使用此函数。
  
|||
|:-----|:-----|
|标头文件：  <br/> |abhelp  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
HRESULT HrOpenABEntryWithSupport(
  LPMAPISUP lpSup,
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPCIID  lpInterface,
  ULONG  ulFlags,
  ULONG FAR * lpulObjType,
  LPUNKNOWN FAR * lppUnk
);
```

## <a name="parameters"></a>参数

 _lpSup_
  
> 
    
 _cbEntryID_
  
> 实时由_lpEntryID_参数指定的条目标识符的字节数。 
    
 _lpEntryID_
  
> 实时指向表示要打开的通讯簿条目的条目标识符的指针。
    
 _lpInterface_
  
>  实时指向接口标识符 (IID) 的指针, 该接口用于访问打开的条目。 传递 NULL 将返回对象的标准接口。 对于邮件用户, 标准接口为[IMailUser: IMAPIProp](imailuserimapiprop.md)。 对于通讯组列表, 它是[IDistList: IMAPIContainer](idistlistimapicontainer.md), 而对于容器, 它是[IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)。 呼叫者可将_lpInterface_设置为相应的标准接口或继承层次结构中的接口。 
    
 _ulFlags_
  
> 实时用于控制_lpszButtonText_参数文本类型的标志的位掩码。 可以设置以下标志: 
    
AB_TELL_DETAILS_CHANGE
  
> 指示如果实际对地址进行了更改, 则详细信息返回 TRUE; 否则返回 false。否则, 详细信息将返回 FALSE。
    
DIALOG_MODAL
  
> 显示 "常用地址" 对话框的模式版本。 此标志与 DIALOG_SDI 互斥。
    
DIALOG_SDI
  
> 显示 "常用地址" 对话框的无模式版本。 此标志与 DIALOG_MODAL 互斥。
    
MAPI_UNICODE
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。
    
 _lpulObjType_
  
> 排除指向已打开条目的类型的指针。
    
 _lppUnk_
  
> 排除指向已打开条目的指针的指针。
    

