---
title: 表单配置文件的文件格式
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 86e4ebd9-6df2-4346-9ce9-580f80a83884
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d07d88d7b8b892a82832f91989e322ea3b32e040
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334823"
---
# <a name="file-format-of-form-configuration-files"></a><span data-ttu-id="7eee3-103">表单配置文件的文件格式</span><span class="sxs-lookup"><span data-stu-id="7eee3-103">File format of form configuration files</span></span>

<span data-ttu-id="7eee3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7eee3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7eee3-105">表单配置文件是由表单开发人员创建的格式文件, 用于定义表单。</span><span class="sxs-lookup"><span data-stu-id="7eee3-105">A form configuration file is a formatted file created by form developers to define a form.</span></span>
  
<span data-ttu-id="7eee3-106">由于表单管理器使用表单配置文件来加载表单, 因此必须使用表单配置文件定义每个表单。</span><span class="sxs-lookup"><span data-stu-id="7eee3-106">Because form configuration files are used by form managers to load forms, each form must be defined using a form configuration file.</span></span> <span data-ttu-id="7eee3-107">表单配置文件的文件扩展名必须为. cfg。</span><span class="sxs-lookup"><span data-stu-id="7eee3-107">Form configuration files must have the .cfg filename extension.</span></span> <span data-ttu-id="7eee3-108">该文件遵循 Windows 初始化文件 (.ini 文件) 的一般语法。</span><span class="sxs-lookup"><span data-stu-id="7eee3-108">The file follows the general syntax of a Windows initialization file (.ini file).</span></span> 

<span data-ttu-id="7eee3-109">它划分为已命名的部分, 每个部分包含一系列条目和值。</span><span class="sxs-lookup"><span data-stu-id="7eee3-109">It is divided into named sections, and each section contains a series of entries and values.</span></span> <span data-ttu-id="7eee3-110">值具有以下类型之一: string、显示的字符串、平台字符串、path、integer 或全局唯一标识符 ( **GUID**)。</span><span class="sxs-lookup"><span data-stu-id="7eee3-110">Values have one of the following types: string, displayed string, platform string, path, integer, or globally unique identifier, **GUID**.</span></span> <span data-ttu-id="7eee3-111">表单配置文件可使用能够保存文本文件的任何文本编辑器或字处理程序创建。</span><span class="sxs-lookup"><span data-stu-id="7eee3-111">Form configuration files can be created with any text editor or word processor that is capable of saving text files.</span></span>
  

