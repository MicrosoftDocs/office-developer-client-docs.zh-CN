---
title: HrOpenABEntryWithProviderUIDSupport
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 1fafc810-7cf3-4c8c-bf21-055ae34da690
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bd42fcd34042c2f9579497f164c4a67f6ba97e35
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775207"
---
# <a name="hropenabentrywithprovideruidsupport"></a>HrOpenABEntryWithProviderUIDSupport

  
  
**适用于**： Outlook 
  
在于**HrOpenABEntryWithProviderUIDSupport**函数打开而不使用会话和通讯簿使用给定的支持对象的条目，请执行[HrOpenABEntryWithProviderUID](hropenabentrywithprovideruid.md)函数相同的功能。 
  
|||
|:-----|:-----|
|头文件：  <br/> |abhelp.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
HRESULT HrOpenABEntryWithProviderUIDSupport(
  const MAPIUID *pEmsabpUID,
  LPMAPISUP lpSup,
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPCIID lpInterface,
  ULONG ulFlags,
  ULONG FAR * lpulObjType,
  LPUNKNOWN FAR * lppUnk
);
```

## <a name="parameters"></a>参数

 _pEmsabpUID_
  
> [in]标识此函数应使用要显示的项标识符的详细信息 Exchange 通讯簿提供程序_emsabpUID_参数指向的指针。 如果传入的项标识符不是 Exchange 通讯簿提供程序条目标识符，则忽略此参数和函数调用并且与[IAddrBook::Details](iaddrbook-details.md)完全一样。 如果此参数为 NULL 或零 MAPIUID，此函数的还行为与[IAddrBook::Details](iaddrbook-details.md)完全相同。
    
 _lpSup_
  
> 
    
 _cbEntryID_
  
> [in]_LpEntryID_参数指定的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]一个指向代表打开的通讯簿条目的项标识符。
    
 _lpInterface_
  
> [in]指向要用于访问打开条目的接口的接口标识符 (IID) 的指针。 传递 NULL 将返回标准接口的对象。 对于邮件用户，标准接口是[IMailUser: IMAPIProp](imailuserimapiprop.md)。 对于通讯组列表它是[IDistList: IMAPIContainer](idistlistimapicontainer.md)，以及是的容器[IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)。 呼叫者可以设置_lpInterface_为相应的标准接口或继承层次结构中的接口。 
    
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
    

