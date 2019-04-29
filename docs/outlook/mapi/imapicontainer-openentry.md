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
  
打开容器中的一个对象, 返回一个接口指针以供进一步访问。
  
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
  
> 实时条目标识符中由_lpEntryID_参数指向的字节数。 
    
 _lpEntryID_
  
> 实时指向要打开的对象的条目标识符的指针。 如果将_lpEntryID_设置为 NULL, 则会打开容器层次结构中的顶级容器。 
    
 _lpInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问对象的接口。 在返回的对象的标准接口的标识符中传递 NULL 结果。 对于邮件, 标准接口为[IMAPIMessageSite: IUnknown](imapimessagesiteiunknown.md);对于文件夹, 它是[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)。 通讯簿对象的标准接口为[IDistList: IMAPIContainer](idistlistimapicontainer.md)对于邮件用户的通讯组列表和[IMailUser: IMAPIProp](imailuserimapiprop.md) 。 
    
 _ulFlags_
  
> 实时用于控制对象打开方式的标志的位掩码。 可以设置以下标志:
    
MAPI_BEST_ACCESS 
  
> 请求将使用用户允许的最大网络权限和最大客户端应用程序访问权限打开对象。 例如, 如果客户端具有读/写权限, 则应以读/写权限打开该对象;如果客户端具有只读访问权限, 则应以只读访问权限打开该对象。 
    
MAPI_DEFERRED_ERRORS 
  
> 允许**OpenEntry**成功返回, 这可能是在对象完全可用于调用客户端之前。 如果该对象不可用, 则进行后续的对象调用可能会引发错误。 
    
MAPI_MODIFY 
  
> 请求读取/写入权限。 默认情况下, 将使用只读访问权限打开对象, 并且客户端不应在假定已授予读/写权限时才起作用。 
    
SHOW_SOFT_DELETES
  
> 显示当前标记为软删除的项目, 即它们处于 "已删除邮件" 保留时间阶段。
    
 _lpulObjType_
  
> 排除指向打开的对象的类型的指针。
    
 _lppUnk_
  
> 排除指向指向用于访问 open 对象的接口实现的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开对象。
    
MAPI_E_NO_ACCESS 
  
> 用户的权限不足, 无法打开该对象, 或试图打开具有读/写权限的只读对象。
    
MAPI_E_NOT_FOUND 
  
> _lpEntryID_指定的条目标识符不代表对象。 
    
MAPI_E_UNKNOWN_ENTRYID 
  
> _lpEntryID_参数中的条目标识符不是容器可识别的格式。 
    
## <a name="remarks"></a>说明

**IMAPIContainer:: OpenEntry**方法在整个容器中打开一个对象, 并返回指向接口实现的指针, 以供进一步访问。 
  
## <a name="notes-to-callers"></a>给调用方的说明

由于服务提供程序不需要返回由_lpInterface_参数中的接口标识符指定的类型的接口实现, 因此请检查_lpulObjType_参数所指向的值。 如有必要, 将_lppUnk_中返回的指针转换为适当类型的指针。 
  
默认情况下, 服务提供程序打开具有只读访问的对象, 除非您设置 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志。 如果设置了其中一个标志, 则服务提供程序将尝试返回一个可修改的对象。 但是, 不要假定, 因为您请求了一个可修改的对象, 而该对象已打开对象具有读/写权限。 计划后续修改失败或检索对象的**PR_ACCESS_LEVEL**属性以确定**OpenEntry**授予的访问级别的机会。
  
## <a name="see-also"></a>另请参阅



[IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md)

