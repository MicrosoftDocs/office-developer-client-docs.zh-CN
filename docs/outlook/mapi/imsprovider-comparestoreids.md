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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317267"
---
# <a name="imsprovidercomparestoreids"></a>IMSProvider::CompareStoreIDs

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
比较两个邮件存储区条目标识符, 以确定它们是否引用同一个存储对象。
  
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
  
> 实时由_lpEntryID1_参数指向的条目标识符的大小 (以字节为单位) _。_
    
 _lpEntryID1_
  
> 实时指向要比较的第一个条目标识符的指针。
    
 _cbEntryID2_
  
> 实时由_lpEntryID2_参数指向的条目标识符的大小 (以字节为单位) _。_
    
 _lpEntryID2_
  
> 实时指向要比较的第二个条目标识符的指针。
    
 _ulFlags_
  
> 实时保留必须为零。
    
 _lpulResult_
  
> 排除指向比较的返回结果的指针。 如果两个条目标识符引用同一个对象, 则为 TRUE; 否则为 false。否则为 FALSE。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>注解

MAPI 在处理对[IMAPISession:: OpenMsgStore](imapisession-openmsgstore.md)方法的调用时调用**IMSProvider:: CompareStoreIDs**方法。 此时, 将调用**CompareStoreIDs** , 以确定哪个配置文件部分 (如果有) 与要打开的邮件存储区相关联。 当没有打开特定存储提供程序的邮件存储区时, 可以进行**CompareStoreIDs**调用。 此外, MAPI 还会在处理对[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)方法的存储提供程序调用时调用**CompareStoreIDs** 。 
  
由**CompareStoreIDs**进行比较的条目标识符均适用于当前存储提供程序的动态链接库 (DLL), 并且都是已包装的存储项标识符。 有关包装存储项标识符的详细信息, 请参阅[IMAPISupport:: WrapStoreEntryID](imapisupport-wrapstoreentryid.md)。
  
比较条目标识符很有用, 因为一个对象可以有多个有效的条目标识符。 例如, 在安装了新版本的邮件存储提供程序后, 可能会发生这种情况。 
  
## <a name="see-also"></a>另请参阅



[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)
  
[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)
  
[IMAPISupport::WrapStoreEntryID](imapisupport-wrapstoreentryid.md)
  
[IMSProvider : IUnknown](imsprovideriunknown.md)

