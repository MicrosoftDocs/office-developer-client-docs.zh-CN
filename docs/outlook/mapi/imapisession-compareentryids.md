---
title: IMAPISessionCompareEntryIDs
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.CompareEntryIDs
api_type:
- COM
ms.assetid: 319f10e9-db8d-4d16-aa1f-6cf5fef493eb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 745c1b10cbbb24389cace7911d7c5fd37fe09472
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586849"
---
# <a name="imapisessioncompareentryids"></a>IMAPISession::CompareEntryIDs

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
比较两个条目标识符来确定它们是否引用同一个对象。 
  
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
  
> [in]在_lpEntryID1_参数指向的项标识符的字节数。 
    
 _lpEntryID1_
  
> [in]指向要进行比较的第一个条目标识符的指针。
    
 _cbEntryID2_
  
> [in]在_lpEntryID2_参数指向的项标识符的字节数。 
    
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
  
> 一个或两个条目标识符指定为参数引用不是对象，可能是因为这些对象是当前未打开和不可用。
    
## <a name="remarks"></a>注解

**IMAPISession::CompareEntryIDs**方法比较两个条目标识符属于单个服务提供程序确定它们是否引用同一个对象。 MAPI [MAPIUID](mapiuid.md)部分提取条目标识符，以确定服务提供程序负责对象，然后调用其登录对象**CompareEntryIDs**方法以执行比较。 
  
## <a name="notes-to-callers"></a>给调用方的说明

**CompareEntryIDs**方法很有用，因为对象可以有多个有效项标识符。 例如，安装新版本的服务提供商之后，会发生这种情况。 
  
如果**CompareEntryIDs**返回一个错误，不会根据比较结果的任何操作。 相反，可能需要最保守的方法。 如果一个或两个条目标识符，如包含无效的**MAPIUID**， **CompareEntryIDs**可能会失败。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|BaseDialog.cpp  <br/> |CbaseDialog::OnCompareEntryIDs  <br/> |MFCMAPI 使用**IMAPISession::CompareEntryIDs**方法比较用户输入的两个条目 Id。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

