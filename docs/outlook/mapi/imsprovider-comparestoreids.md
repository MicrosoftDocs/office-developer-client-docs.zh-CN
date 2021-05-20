---
title: IMSProviderCompareStoreIDs
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSProvider.CompareStoreIDs
api_type:
- COM
ms.assetid: c3e3cfaa-9c4a-482a-9411-9c4ab01d312f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 734e53c1e897c902c72319aa6f2d3d7af2d23fb6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431706"
---
# <a name="imsprovidercomparestoreids"></a>IMSProvider::CompareStoreIDs

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
比较两个邮件存储条目标识符以确定它们是否引用同一存储对象。
  
```cpp
HRESULT CompareStoreIDs(
  ULONG cbEntryID1,
  LPENTRYID lpEntryID1,
  ULONG cbEntryID2,
  LPENTRYID lpEntryID2,
  ULONG ulFlags,
  ULONG FAR * lpulResult
);
```

## <a name="parameters"></a>参数

 _cbEntryID1_
  
> [in]  _lpEntryID1_ 参数指向的条目标识符的大小（以字节为单位  _）。_
    
 _lpEntryID1_
  
> [in]指向要比较的第一个条目标识符的指针。
    
 _cbEntryID2_
  
> [in]  _lpEntryID2_ 参数指向的条目标识符的大小（以字节为单位  _）。_
    
 _lpEntryID2_
  
> [in]指向要比较的第二个条目标识符的指针。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpulResult_
  
> [out]指向比较结果的返回结果的指针。 如果两个条目标识符引用同一个对象，则其为 TRUE;否则为 FALSE。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

MAPI 在处理对 [IMAPISession：：OpenMsgStore](imapisession-openmsgstore.md)方法的调用时调用 **IMSProvider：：CompareStoreIDs** 方法。 **此时将调用 CompareStoreIDs** 以确定哪个配置文件部分（如果有）与正在打开的邮件存储相关联。 当没有为特定存储提供程序打开任何邮件存储时，可以调用 **CompareStoreIDs。** 此外，MAPI 还会在处理对 [IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md)方法的存储提供程序调用时调用 **CompareStoreIDs。** 
  
**CompareStoreIDs** 比较的条目标识符既适用于当前存储提供程序的动态链接库 (DLL) ，又都是未包存储条目标识符。 有关包装存储条目标识符的信息，请参阅 [IMAPISupport：：WrapStoreEntryID](imapisupport-wrapstoreentryid.md)。
  
比较条目标识符非常有用，因为对象可以具有多个有效的条目标识符。 例如，安装邮件存储提供程序的新版本后，可能会发生这种情况。 
  
## <a name="see-also"></a>另请参阅



[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)
  
[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)
  
[IMAPISupport::WrapStoreEntryID](imapisupport-wrapstoreentryid.md)
  
[IMSProvider : IUnknown](imsprovideriunknown.md)

