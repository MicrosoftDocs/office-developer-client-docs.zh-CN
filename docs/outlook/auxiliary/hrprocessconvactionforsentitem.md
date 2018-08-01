---
title: HrProcessConvActionForSentItem
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 08121e33-7820-4a31-b6da-06a4a54ec43f
description: 根据其 pidtagconversationid 对应邮件项目上执行后发送分类。
ms.openlocfilehash: efecfc2d0d865428cb958fc15a858bbc7807c5d1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774200"
---
# <a name="hrprocessconvactionforsentitem"></a>HrProcessConvActionForSentItem

根据其[pidtagconversationid 对应](http://msdn.microsoft.com/library/f8e4a5fa-cb73-4eca-b174-72e1fda821a6%28Office.15%29.aspx)邮件项目上执行后发送分类。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|导出：  <br/> |Outlook.exe  <br/> |
|调用：  <br/> |客户端  <br/> |
|通过实现：  <br/> |Outlook  <br/> |
   
```cpp
HRESULT WINAPI HrProcessConvActionForSentItem( 
    SBinary const *pmbinStoreEid, 
    SBinary const *pmbinMsgEid, 
    SBinary const *pmbinConvID, 
    DWORD dwFlags)
```

## <a name="parameters"></a>参数

_pmbinStoreEid_
  
> [in]存储区或邮件项目的[PidTagStoreEntryId](http://msdn.microsoft.com/library/0d705667-19f4-4eda-a068-e65ea8f00d9b%28Office.15%29.aspx) [PidTagEntryId](http://msdn.microsoft.com/library/ca02e873-c2d2-4d58-8df8-c05fbcdc8fba%28Office.15%29.aspx) 。 不能为 NULL 或无效。 
    
_pmbinMsgEid_
  
> [in]邮件项目[PidTagEntryId](http://msdn.microsoft.com/library/ca02e873-c2d2-4d58-8df8-c05fbcdc8fba%28Office.15%29.aspx) 。 不能为 NULL 或无效。 
    
_pmbinConvID_
  
> [in]邮件项目[pidtagconversationid 对应](http://msdn.microsoft.com/library/f8e4a5fa-cb73-4eca-b174-72e1fda821a6%28Office.15%29.aspx)。 不能为 NULL 或无效。 
    
_dwFlags_
  
> [in]一个位掩码，指定有关方法调用的其他信息。
    
   - 0 — 在此方法调用中未使用任何其他选项。 这是建议的值。 
    
   - **PCAFSIF_MSGEID_IS_SEARCH_KEY**— _pmbinMsgEid_是实际[PidTagSearchKey](http://msdn.microsoft.com/library/fcab369a-a1f4-4425-a272-e35046914a4d%28Office.15%29.aspx)的邮件。 使用**PidTagSearchKey**占用资源，并应避免使用[PidTagEntryId](http://msdn.microsoft.com/library/ca02e873-c2d2-4d58-8df8-c05fbcdc8fba%28Office.15%29.aspx)是否可用。 
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |呼叫成功。  <br/> |
|E_INVALIDARG  <br/> | _dwFlags_包含未知的标志。  <br/> |
   
## <a name="remarks"></a>说明

类别被视为个人信息并不应之外的用户的邮箱传输。 因此，不要未发送的邮件项目上调用**HrProcessConvActionForSentItem** 。 相反，将项目，发送，然后在存档的副本上调用**HrProcessConvActionForSentItem** 。 可能会在已发送邮件文件夹中或等效位置存储存档的副本。 
  
您的应用程序必须在过程与 Outlook.exe，例如从 COM 加载项，若要调用**HrProcessConvActionForSentItem**。 如果尝试调用**HrProcessConvActionForSentItem**进程外， **HrProcessConvActionForSentItem**将引发异常访问冲突。 
  

