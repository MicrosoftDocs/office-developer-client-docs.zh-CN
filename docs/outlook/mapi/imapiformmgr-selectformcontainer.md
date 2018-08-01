---
title: IMAPIFormMgrSelectFormContainer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.CopyMessages
api_type:
- COM
ms.assetid: c33daad6-52c4-4968-ac56-415178c9bf12
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ef9b99f06b62fd361bb780debb527ec2d7457589
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775460"
---
# <a name="imapiformmgrselectformcontainer"></a>IMAPIFormMgr::SelectFormContainer

  
  
**适用于**： Outlook 
  
显示一个对话框，使用户能够选择窗体容器，并返回对 container 对象选定的用户界面。
  
```cpp
HRESULT SelectFormContainer(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPMAPIFORMCONTAINER FAR * lppfcnt
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]显示的对话框中的父窗口句柄。 
    
 _ulFlags_
  
> [in]控制如何选择表单库的标志位掩码 （即，如何窗体容器选中）。 可以设置以下标志：
    
MAPIFORM_SELECT_ALL_REGISTRIES 
  
> 可以从所有容器中进行选择。 这是默认所选内容类型。 
    
MAPIFORM_SELECT_FOLDER_REGISTRY_ONLY 
  
> 可以仅从文件夹容器中进行选择。
    
MAPIFORM_SELECT_NON_FOLDER_REGISTRY_ONLY 
  
> 选定内容仅发出未与文件夹关联的容器。
    
 _lppfcnt_
  
> [输出]指向返回的接口的指针的指针。 此接口是用户选择的容器对象。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>说明

表单查看器通常调用**IMAPIFormMgr::SelectFormContainer**方法选择窗体所安装到一个窗体容器。 **SelectFormContainer**不能用于选择本地窗体的容器，具有 HFRMREG_LOCAL 的值。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MainDlg.cpp  <br/> |CMainDlg::OnSelectFormContainer  <br/> |MFCMAPI 使用**IMAPIFormMgr::SelectFormContainer**方法呈现其内容之前选择窗体的容器。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

