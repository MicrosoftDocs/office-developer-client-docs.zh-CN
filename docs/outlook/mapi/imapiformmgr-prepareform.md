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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d0d5d8fe13a3c192dc0b0a8ddc0f5f945fa16f15
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416648"
---
# <a name="imapiformmgrprepareform"></a>IMAPIFormMgr::PrepareForm

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
下载要打开的表单。
  
```cpp
HRESULT PrepareForm(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPMAPIFORMINFO pfrmiInfo
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]下载表单时显示的进度指示器的父窗口的句柄。 除非  _在 ulFlags_ 参数中设置了 MAPI_DIALOG 标志，否则将忽略  _ulUIParam_ 参数。 
    
 _ulFlags_
  
> [in]控制表单下载方式的标志的位掩码。 可以设置以下标志：
    
MAPI_DIALOG 
  
> 显示用户界面以提供状态或提示用户输入详细信息。 如果未设置此标志，则不显示用户界面。
    
 _pfrmiInfo_
  
> [in]指向要下载的表单的表单信息对象的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

表单查看器调用 **IMAPIFormMgr：:P repareForm** 方法，从表单容器下载表单以打开。 大多数表单查看器不需要调用 **PrepareForm，** 因为 [IMAPIFormMgr：：CreateForm](imapiformmgr-createform.md) 和 [IMAPIFormMgr：：LoadForm](imapiformmgr-loadform.md) 方法都调用 **PrepareForm（** 如有必要）。 
  
可以使用 **PrepareForm** 获取 DLL 中的动态链接库 (DLL) 与表单关联的其他文件来修改它们。 如果修改后的表单加载回其表单容器，则必须重新安装该表单。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFormMgr::CreateForm](imapiformmgr-createform.md)
  
[IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)

