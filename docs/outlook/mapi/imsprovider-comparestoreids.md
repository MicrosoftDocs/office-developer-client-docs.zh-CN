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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 57b8438d655b3bc5b708fd7ed6734554a3a23ac4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585988"
---
# <a name="imsprovidercomparestoreids"></a>IMSProvider::CompareStoreIDs

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
比较两个邮件存储条目标识符，以确定它们是否引用同一个 store 对象。
  
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
  
> [in]大小，以字节为单位的项标识符_lpEntryID1_参数指向 _。_
    
 _lpEntryID1_
  
> [in]指向要进行比较的第一个条目标识符的指针。
    
 _cbEntryID2_
  
> [in]大小，以字节为单位的项标识符_lpEntryID2_参数指向 _。_
    
 _lpEntryID2_
  
> [in]指向要进行比较的第二个条目标识符的指针。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpulResult_
  
> [输出]一个指向的比较结果返回的结果。 如果两个条目标识符引用同一对象，则为 TRUE否则为返回 FALSE。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>注解

处理调用[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)方法时，MAPI 调用**IMSProvider::CompareStoreIDs**方法。 此时调用**CompareStoreIDs** ，以确定哪些配置文件部分中，如果有，关联与在打开的消息存储。 打开特定存储提供程序没有邮件存储区时，可以进行**CompareStoreIDs**调用。 此外，MAPI 还调用**CompareStoreIDs**处理存储提供程序调用[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)方法时。 
  
通过**CompareStoreIDs**比较的项标识符是同时为当前存储提供程序的动态链接库 (DLL) 和都是解包的存储项标识符。 有关环绕存储项标识符的详细信息，请参阅[IMAPISupport::WrapStoreEntryID](imapisupport-wrapstoreentryid.md)。
  
比较条目标识符很有用，因为对象可以有多个有效项标识符。 这可能会发生，例如，安装新版本的消息存储提供程序。 
  
## <a name="see-also"></a>另请参阅



[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)
  
[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)
  
[IMAPISupport::WrapStoreEntryID](imapisupport-wrapstoreentryid.md)
  
[IMSProvider : IUnknown](imsprovideriunknown.md)

