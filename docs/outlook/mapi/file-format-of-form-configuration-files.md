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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415549"
---
# <a name="file-format-of-form-configuration-files"></a><span data-ttu-id="fecd4-103">表单配置文件的文件格式</span><span class="sxs-lookup"><span data-stu-id="fecd4-103">File format of form configuration files</span></span>

<span data-ttu-id="fecd4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fecd4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fecd4-105">表单配置文件是由表单开发人员创建的用于定义表单的格式化文件。</span><span class="sxs-lookup"><span data-stu-id="fecd4-105">A form configuration file is a formatted file created by form developers to define a form.</span></span>
  
<span data-ttu-id="fecd4-106">由于表单管理员使用表单配置文件来加载表单，因此必须使用表单配置文件定义每个表单。</span><span class="sxs-lookup"><span data-stu-id="fecd4-106">Because form configuration files are used by form managers to load forms, each form must be defined using a form configuration file.</span></span> <span data-ttu-id="fecd4-107">表单配置文件必须具有 .cfg 文件名扩展名。</span><span class="sxs-lookup"><span data-stu-id="fecd4-107">Form configuration files must have the .cfg filename extension.</span></span> <span data-ttu-id="fecd4-108">该文件遵循文件初始化文件Windows的 (.ini语法) 。</span><span class="sxs-lookup"><span data-stu-id="fecd4-108">The file follows the general syntax of a Windows initialization file (.ini file).</span></span> 

<span data-ttu-id="fecd4-109">它分为多个命名部分，每个节包含一系列项和值。</span><span class="sxs-lookup"><span data-stu-id="fecd4-109">It is divided into named sections, and each section contains a series of entries and values.</span></span> <span data-ttu-id="fecd4-110">值具有以下类型之一：字符串、显示字符串、平台字符串、路径、整数或全局唯一标识符 **GUID。**</span><span class="sxs-lookup"><span data-stu-id="fecd4-110">Values have one of the following types: string, displayed string, platform string, path, integer, or globally unique identifier, **GUID**.</span></span> <span data-ttu-id="fecd4-111">可以使用能够保存文本文件的任何文本编辑器或字处理器创建表单配置文件。</span><span class="sxs-lookup"><span data-stu-id="fecd4-111">Form configuration files can be created with any text editor or word processor that is capable of saving text files.</span></span>
  

