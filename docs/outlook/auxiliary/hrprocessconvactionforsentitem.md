---
title: HrProcessConvActionForSentItem
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 08121e33-7820-4a31-b6da-06a4a54ec43f
description: 基于邮件项的 PidTagConversationId 对邮件项目执行发送后分类。
ms.openlocfilehash: 675f308093eea30084271abc66c1fa66e2ad6828
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318898"
---
# <a name="hrprocessconvactionforsentitem"></a>HrProcessConvActionForSentItem

基于邮件项目的 [PidTagConversationId 对邮件项目执行发送后分类](https://msdn.microsoft.com/library/f8e4a5fa-cb73-4eca-b174-72e1fda821a6%28Office.15%29.aspx)。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|导出者：  <br/> |Outlook.exe  <br/> |
|调用者：  <br/> |客户端  <br/> |
|实现者：  <br/> |Outlook  <br/> |
   
```cpp
HRESULT WINAPI HrProcessConvActionForSentItem( 
    SBinary const *pmbinStoreEid, 
    SBinary const *pmbinMsgEid, 
    SBinary const *pmbinConvID, 
    DWORD dwFlags)
```

## <a name="parameters"></a>参数

_pmbinStoreEid_
  
> [in]存储[的 PidTagEntryId](https://msdn.microsoft.com/library/ca02e873-c2d2-4d58-8df8-c05fbcdc8fba%28Office.15%29.aspx)或邮件项目的[PidTagStoreEntryId。](https://msdn.microsoft.com/library/0d705667-19f4-4eda-a068-e65ea8f00d9b%28Office.15%29.aspx) 不能为 NULL 或无效。 
    
_pmbinMsgEid_
  
> [in]邮件[项目的 PidTagEntryId。](https://msdn.microsoft.com/library/ca02e873-c2d2-4d58-8df8-c05fbcdc8fba%28Office.15%29.aspx) 不能为 NULL 或无效。 
    
_pmbinConvID_
  
> [in]邮件[项目的 PidTagConversationId。](https://msdn.microsoft.com/library/f8e4a5fa-cb73-4eca-b174-72e1fda821a6%28Office.15%29.aspx) 不能为 NULL 或无效。 
    
_dwFlags_
  
> [in]一个位掩码，用于指定有关方法调用的其他信息。
    
   - 0 - 此方法调用中未使用任何其他选项。 这是建议的值。 
    
   - **PCAFSIF_MSGEID_IS_SEARCH_KEY** _- pmbinMsgEid_ 实际上是邮件的 [PidTagSearchKey。](https://msdn.microsoft.com/library/fcab369a-a1f4-4425-a272-e35046914a4d%28Office.15%29.aspx) 使用 **PidTagSearchKey** 会消耗大量资源，如果 [PidTagEntryId 可用，应避免使用 PidTagEntryId。](https://msdn.microsoft.com/library/ca02e873-c2d2-4d58-8df8-c05fbcdc8fba%28Office.15%29.aspx) 
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |呼叫成功。  <br/> |
|E_INVALIDARG  <br/> | _dwFlags_ 包含未知标志。  <br/> |
   
## <a name="remarks"></a>备注

类别被视为个人信息，不应在用户的邮箱外部传输。 因此，不要对未发送的邮件项目调用 **HrProcessConvActionForSentItem。** 相反，发送该项目，然后在存档副本上 **调用 HrProcessConvActionForSentItem。** 存档副本可能存储在"已发送的项目"文件夹中或等效位置。 
  
您的应用程序必须在处理过程中Outlook.exe，如从 COM 加载项调用 **HrProcessConvActionForSentItem。** 如果尝试在进程外调用 **HrProcessConvActionForSentItem，HrProcessConvActionForSentItem** 将引发访问冲突异常。  
  

