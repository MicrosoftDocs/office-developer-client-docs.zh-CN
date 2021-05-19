---
title: IMAPIContainerOpenEntry
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIContainer.OpenEntry
api_type:
- COM
ms.assetid: 0c46c1fb-dd63-4ac5-960e-80f68e75d8f4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9598e0c90c16db14cdc3a46d2b2ae74e0d9a9300
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423634"
---
# <a name="imapicontaineropenentry"></a>IMAPIContainer::OpenEntry

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开容器中的对象，返回接口指针以进一步访问。
  
```cpp
HRESULT OpenEntry(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPCIID lpInterface,
  ULONG ulFlags,
  ULONG FAR * lpulObjType,
  LPUNKNOWN FAR * lppUnk
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。 
    
 _lpEntryID_
  
> [in]指向要打开的对象的条目标识符的指针。 如果  _lpEntryID_ 设置为 NULL，则打开容器层次结构中的顶级容器。 
    
 _lpInterface_
  
> [in]指向接口标识符的指针 (IID) 表示用于访问对象的接口。 传递 NULL 会导致返回对象的标准接口的标识符。 对于消息，标准接口是 [IMAPIMessageSite ： IUnknown](imapimessagesiteiunknown.md);对于文件夹，它是 [IMAPIFolder ： IMAPIContainer](imapifolderimapicontainer.md)。 通讯簿对象的标准接口是 [IDistList ： IMAPIContainer](idistlistimapicontainer.md) 表示通讯组列表和 [IMailUser ： IMAPIProp](imailuserimapiprop.md) 消息用户。 
    
 _ulFlags_
  
> [in]控制对象打开方式的标志的位掩码。 可以设置以下标志：
    
MAPI_BEST_ACCESS 
  
> 请求以用户允许的最大网络权限和最大客户端应用程序访问权限打开对象。 例如，如果客户端具有读/写权限，则应该使用读/写权限打开对象;如果客户端具有只读访问权限，则应该以只读访问权限打开对象。 
    
MAPI_DEFERRED_ERRORS 
  
> 允许 **OpenEntry** 在对象完全可供调用客户端使用之前成功返回。 如果该对象不可用，则进行后续对象调用可能会引发错误。 
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，使用只读访问权限打开对象，客户端不应在已授予读/写权限的假设下工作。 
    
SHOW_SOFT_DELETES
  
> 显示当前标记为软删除的项目，即它们处于已删除项目的保留时间阶段。
    
 _lpulObjType_
  
> [out]指向已打开对象的类型的指针。
    
 _lppUnk_
  
> [out]指向用于访问打开对象的接口实现指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开对象。
    
MAPI_E_NO_ACCESS 
  
> 用户没有足够的权限打开对象，或者试图打开具有读/写权限的只读对象。
    
MAPI_E_NOT_FOUND 
  
> _lpEntryID_ 指定的条目标识符不表示对象。 
    
MAPI_E_UNKNOWN_ENTRYID 
  
> _lpEntryID_ 参数中的条目标识符不是容器识别的格式。 
    
## <a name="remarks"></a>备注

**IMAPIContainer：：OpenEntry** 方法在整个容器中打开一个对象，并返回指向接口实现以用于进一步访问的指针。 
  
## <a name="notes-to-callers"></a>给调用方的说明

由于服务提供商不需要返回  _由 lpInterface_ 参数中的接口标识符指定的类型的接口实现，请检查  _lpulObjType_ 参数指向的值。 如有必要，将  _lppUnk_ 中返回的指针强制转换到相应类型的指针。 
  
默认情况下，服务提供商打开具有只读访问权限的对象，除非您设置 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志。 当设置其中一个标志时，服务提供商会尝试返回一个可修改的对象。 但是，不要假定由于您请求了一个可修改对象，而打开的对象具有读/写权限。 无论是规划后续修改失败的可能性，还是检索对象的 **PR_ACCESS_LEVEL** 属性来确定 **OpenEntry 授予的访问级别**。
  
## <a name="see-also"></a>另请参阅



[IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md)

