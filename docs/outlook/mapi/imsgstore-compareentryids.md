---
title: IMsgStoreCompareEntryIDs
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.CompareEntryIDs
api_type:
- COM
ms.assetid: 33d70748-0d3f-4be4-bcb5-7ec048887944
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 640923511241b08e5a86e9733aab5cc2e9237c23
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576573"
---
# <a name="imsgstorecompareentryids"></a>IMsgStore::CompareEntryIDs

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
比较两个条目标识符来确定它们是否引用中的消息存储的同一个条目。 MAPI 将传递到的服务提供此呼叫，仅当要比较两个条目 identifiers 中的唯一标识符 (Uid) 处理该服务提供商。
  
```cpp
HRESULT CompareEntryIDs(
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
  
> [in]_LpEntryID1_参数 _。_ 指向该条目标识符中字节数
    
 _lpEntryID1_
  
> [in]指向要进行比较的第一个条目标识符的指针。
    
 _cbEntryID2_
  
> [in]_LpEntryID2_参数 _。_ 指向该条目标识符中字节数
    
 _lpEntryID2_
  
> [in]指向要进行比较的第二个条目标识符的指针。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpulResult_
  
> [输出]一个指向比较结果的结果。 如果两个条目标识符引用同一对象，则为 TRUE否则为返回 FALSE。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 比较成功。
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 显示一个或两个条目标识符指定为参数引用不是对象，可能是因为相应的对象未打开，并在不可用。
    
## <a name="remarks"></a>注解

**IMsgStore::CompareEntryIDs**方法比较两个条目标识符属于要确定它们是否引用同一个对象的消息存储。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **CompareEntryIDs**很有用，因为对象可以有多个有效项标识符 （例如，安装新版本的消息存储提供程序后）。 
  
如果**CompareEntryIDs**返回一个错误，不会根据比较结果的任何操作。 相反，可能需要最保守的方法。 如果一个或两个条目标识符，如包含无效的**MAPIUID**， **CompareEntryIDs**可能会失败。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|BaseDialog.cpp  <br/> |CBaseDialog::OnCompareEntryIDs  <br/> |MFCMAPI 使用**IMsgStore::CompareEntryIDs**方法比较条目 Id。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

