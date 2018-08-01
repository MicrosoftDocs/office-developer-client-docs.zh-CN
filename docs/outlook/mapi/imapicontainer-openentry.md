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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c13ab9ce9c2564c39bfe9b2689f05439bc7b74ff
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775314"
---
# <a name="imapicontaineropenentry"></a>IMAPIContainer::OpenEntry

  
  
**适用于**： Outlook 
  
在该容器，返回进一步访问的接口指针中打开一个对象。
  
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
  
> [in]在_lpEntryID_参数指向的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]指向要打开的对象的项标识符的指针。 如果_lpEntryID_设置为 NULL，则打开容器的层次结构中的顶级容器。 
    
 _lpInterface_
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问该对象的接口的指针。 传递空结果中要返回的对象的标准接口的标识符。 对于消息，标准接口是[IMAPIMessageSite: IUnknown](imapimessagesiteiunknown.md);对于文件夹，它是[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)。 标准接口的地址簿对象是[IDistList: IMAPIContainer](idistlistimapicontainer.md)通讯组列表和[IMailUser: IMAPIProp](imailuserimapiprop.md)消息用户。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何打开对象。 可以设置以下标志：
    
MAPI_BEST_ACCESS 
  
> 请求将使用用户和最大客户端应用程序访问允许的最大网络权限打开对象。 例如，如果客户端具有读/写权限，该对象应打开具有读/写权限;如果客户端具有只读访问权限，则应具有只读访问权限打开对象。 
    
MAPI_DEFERRED_ERRORS 
  
> 允许**OpenEntry**返回成功，原因可能是完全可调用客户端对象之前。 如果对象不可用，则进行后续对象呼叫会引发错误。 
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，对象打开具有只读访问权限和客户端不应以为，读/写权限授予起作用。 
    
SHOW_SOFT_DELETES
  
> 显示项目的当前标记为软删除 — 即，它们是中已删除的邮件保留时间阶段。
    
 _lpulObjType_
  
> [输出]一个指向打开的对象的类型。
    
 _lppUnk_
  
> [输出]指向该接口实现用于访问打开的对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功打开对象。
    
MAPI_E_NO_ACCESS 
  
> 用户具有权限不足，无法打开的对象，或尝试打开只读对象具有读/写权限。
    
MAPI_E_NOT_FOUND 
  
> 指定_lpEntryID_的项标识符不代表一个对象。 
    
MAPI_E_UNKNOWN_ENTRYID 
  
> _LpEntryID_参数中的项标识符不是格式的容器识别。 
    
## <a name="remarks"></a>说明

**IMAPIContainer::OpenEntry**方法打开整个容器对象，并返回到接口实现用于进一步访问的指针。 
  
## <a name="notes-to-callers"></a>给调用方的说明

由于无需服务提供程序返回的接口标识符_lpInterface_参数中指定的类型的接口实现，检查指向_lpulObjType_参数的值。 如有必要，强制转换中_lppUnk_返回到适当类型的指针的指针。 
  
默认情况下，服务提供商对象使用只读访问权限打开如果设置 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志。 当这些标志之一设置时，服务提供商将尝试返回可修改对象。 但是，不假定，因为请求一个可修改的对象，该对象打开的对象具有读/写权限。 通过规划的后续修改失败或检索对象的**PR_ACCESS_LEVEL**属性确定**OpenEntry**授予的访问级别的机会。
  
## <a name="see-also"></a>另请参阅



[IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md)

