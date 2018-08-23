---
title: IMAPIFormMgrPrepareForm
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr.PrepareForm
api_type:
- COM
ms.assetid: 8f8ee2cb-1c2a-4958-b01e-2f4aab689f89
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6e8ea7230ae86dee99cc4413715055fc53afa900
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579723"
---
# <a name="imapiformmgrprepareform"></a>IMAPIFormMgr::PrepareForm

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
下载用于打开的表单。
  
```cpp
HRESULT PrepareForm(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPMAPIFORMINFO pfrmiInfo
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]下载表单时显示进度指示器的父窗口句柄。 除非 MAPI_DIALOG 标志设置_ulFlags_参数中，将忽略该_ulUIParam_参数。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何下载窗体。 可以设置以下标记：
    
MAPI_DIALOG 
  
> 显示用户界面，以提供状态或提示用户输入的详细信息。 如果未设置此标志，将显示没有用户界面。
    
 _pfrmiInfo_
  
> [in]指向要下载的窗体的窗体信息对象的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>注解

表单查看器调用**IMAPIFormMgr::PrepareForm**方法从打开的窗体容器下载窗体。 大多数表单查看器不需要调用**PrepareForm**，因为[IMAPIFormMgr::CreateForm](imapiformmgr-createform.md)和[IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md)方法调用**PrepareForm**，如有必要。 
  
您可以使用**PrepareForm**获取动态链接库 (Dll) 和修改其表单相关联的其他文件。 如果回其窗体容器加载修改窗体时，必须重新安装。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFormMgr::CreateForm](imapiformmgr-createform.md)
  
[IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)

