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
ms.openlocfilehash: 58a6249295810e32c0a0f845e4830b8f393885ba
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579380"
---
# <a name="hropenabentrywithsupport"></a>HrOpenABEntryWithSupport

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
不要使用此函数。
  
|||
|:-----|:-----|
|头文件：  <br/> |abhelp.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]_LpEntryID_参数指定的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]一个指向代表打开的通讯簿条目的项标识符。
    
 _lpInterface_
  
>  [in]指向要用于访问打开条目的接口的接口标识符 (IID) 的指针。 传递 NULL 将返回标准接口的对象。 对于邮件用户，标准接口是[IMailUser: IMAPIProp](imailuserimapiprop.md)。 对于通讯组列表，它是[IDistList: IMAPIContainer](idistlistimapicontainer.md)，而容器，则为： [IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)。 呼叫者可以设置_lpInterface_为相应的标准接口或继承层次结构中的接口。 
    
 _ulFlags_
  
> [in]位掩码的标志的控制_lpszButtonText_参数的文本的类型。 可以设置以下标志： 
    
AB_TELL_DETAILS_CHANGE
  
> 指示详细信息返回 TRUE 是否进行了更改实际的地址;否则，详细信息将返回 FALSE。
    
DIALOG_MODAL
  
> 显示模式版本的通用的地址对话框。 此标志是与 DIALOG_SDI 互斥。
    
DIALOG_SDI
  
> 显示通用的地址对话框的无模式版本。 此标志是与 DIALOG_MODAL 互斥。
    
MAPI_UNICODE
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。
    
 _lpulObjType_
  
> [输出]一个指向打开条目的类型。
    
 _lppUnk_
  
> [输出]指向打开的条目的指针的指针。
    

