---
title: LOC 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251455
localization_priority: Normal
ms.assetid: 7db7a8ed-50a9-8495-b978-42a2fddb466a
description: 获取一个形状的本地坐标中定义的点，并返回以与公式相关联的形状的本地坐标表示的等效点。
ms.openlocfilehash: 196e2c92ea6ab410b6ecca9767b68605e4eb4d30
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780607"
---
# <a name="loc-function-visioshapesheet"></a>LOC 函数 (VisioShapeSheet)

获取一个形状的本地坐标中定义的点，并返回以与公式相关联的形状的本地坐标表示的等效点。 
  
## <a name="syntax"></a>语法

LOC (* **指向** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _点_ <br/> |必需  <br/> |**字符串** <br/> | 一个形状的本地坐标中定义的点。  <br/> |
   
### <a name="return-value"></a>返回值

String
  
## <a name="remarks"></a>注解

本地坐标是以形状的选择矩形的左下角为基准测量的。两个形状必须在同一页上。
  
## <a name="example"></a>示例

LOC (PNT (Sheet.5 ！LocPinX，Sheet.5 ！LocPinY)) 
  
在此表达式中，PNT 将 Sheet.5 中的一组本地坐标转换为一个点。（Sheet.5 是同一绘图页上的另一个形状。）然后，LOC 相对于当前形状的选择矩形的左下角，将这个点转换为当前形状的本地坐标系中的等效点。 
  
Sheet.5 中的 5 是形状，其显示在**形状名**对话框 （**开发人员**选项卡） 中的 ID 号。 
  

