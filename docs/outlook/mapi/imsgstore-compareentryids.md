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
ms.openlocfilehash: 2a2439bae79b497f018391983e2c4b03a35eee70
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424250"
---
# <a name="imsgstorecompareentryids"></a>IMsgStore::CompareEntryIDs

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
比较两个条目标识符以确定它们是否引用邮件存储中的同一条目。 MAPI 仅在要比较的两个条目标识符 (UID) 唯一标识符由该提供程序处理时，才将此调用传递给服务提供商。
  
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
  
> [in]  _lpEntryID1_ 参数指向的条目标识符中的字节计数  _。_
    
 _lpEntryID1_
  
> [in]指向要比较的第一个条目标识符的指针。
    
 _cbEntryID2_
  
> [in]  _lpEntryID2_ 参数指向的条目标识符中的字节计数  _。_
    
 _lpEntryID2_
  
> [in]指向要比较的第二个条目标识符的指针。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpulResult_
  
> [out]指向比较结果的指针。 如果两个条目标识符引用同一个对象，则其为 TRUE;否则为 FALSE。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 比较成功。
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 指定为参数的一个或两个条目标识符不引用对象，可能是因为相应的对象尚未打开并且目前不可用。
    
## <a name="remarks"></a>备注

**IMsgStore：：CompareEntryIDs** 方法比较属于邮件存储的两个条目标识符，以确定它们是否引用同一个对象。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **CompareEntryIDs** 非常有用，因为对象可以具有多个有效的条目标识符 (例如，在邮件存储提供程序的新版本安装之后) 。 
  
如果 **CompareEntryIDs** 返回错误，请不要根据比较结果执行任何操作。 相反，尽可能采用最保守的方法。 例如，如果一个或两个条目标识符包含无效 **的 MAPIUID** **，CompareEntryIDs** 可能会失败。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|BaseDialog.cpp  <br/> |CBaseDialog：：OnCompareEntryIDs  <br/> |MFCMAPI 使用 **IMsgStore：：CompareEntryIDs** 方法来比较条目 ID。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

