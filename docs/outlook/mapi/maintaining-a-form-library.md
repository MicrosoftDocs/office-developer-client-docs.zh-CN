---
title: 维护表单库
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8488f7ec-e44b-4d1a-ba42-baea8c71d350
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 51c7c3f8ba70dcb3d35dc50806e984fd4b193818
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32298458"
---
# <a name="maintaining-a-form-library"></a><span data-ttu-id="2392b-103">维护表单库</span><span class="sxs-lookup"><span data-stu-id="2392b-103">Maintaining a Form Library</span></span>

  
  
<span data-ttu-id="2392b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2392b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2392b-105">表单库包含有关表单的所有重要信息: 其属性、谓词和其服务器的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="2392b-105">A form library holds all of the important information about a form: its properties, its verbs, and its server's executable files.</span></span> <span data-ttu-id="2392b-106">某些客户端允许其用户维护、安装或删除表单服务器。</span><span class="sxs-lookup"><span data-stu-id="2392b-106">Some clients allow their users to maintain, install, or remove form servers.</span></span> <span data-ttu-id="2392b-107">如果要向您的用户提供此功能, 您必须具有以下权限:</span><span class="sxs-lookup"><span data-stu-id="2392b-107">If you want to offer this feature to your users, you must have access to:</span></span>
  
- <span data-ttu-id="2392b-108">表单服务器的配置文件, 带有的文件。CFG 扩展。</span><span class="sxs-lookup"><span data-stu-id="2392b-108">The form server's configuration file, a file with the .CFG extension.</span></span>
    
- <span data-ttu-id="2392b-109">表单库的容器对象, 是一个实现[IMAPIFormContainer: IUnknown](imapiformcontaineriunknown.md)接口的对象。</span><span class="sxs-lookup"><span data-stu-id="2392b-109">The form library's container object, an object that implements the [IMAPIFormContainer : IUnknown](imapiformcontaineriunknown.md) interface.</span></span> 
    
<span data-ttu-id="2392b-110">若要访问配置文件或其路径名, 请使用任何方法都方便。</span><span class="sxs-lookup"><span data-stu-id="2392b-110">To access the configuration file or a pathname to it, use whatever means are convenient.</span></span> <span data-ttu-id="2392b-111">通常情况下, 客户端会向用户显示一个对话框, 用于安装和删除窗体服务器, 该对话框还可用于提示用户输入配置文件的位置。</span><span class="sxs-lookup"><span data-stu-id="2392b-111">Usually, clients present the user with a dialog box for installing and removing form servers that can also be used to prompt the user for the location of the configuration file.</span></span>
  
<span data-ttu-id="2392b-112">若要访问表单库的容器, 请调用表单管理器的[IMAPIFormMgr:: OpenFormContainer](imapiformmgr-openformcontainer.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2392b-112">To access the form library's container, call the form manager's [IMAPIFormMgr::OpenFormContainer](imapiformmgr-openformcontainer.md) method.</span></span> <span data-ttu-id="2392b-113">传入枚举值以指定要打开的表单库, 如有必要, 将指向表单管理器打开表单库时应使用的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="2392b-113">Pass in an enumeration value to specify which form library to open, and if necessary, a pointer to the object that the form manager should use to open the form library.</span></span> <span data-ttu-id="2392b-114">例如, 如果要打开[文件夹表单库](folder-form-libraries.md), 请传递[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)指针。</span><span class="sxs-lookup"><span data-stu-id="2392b-114">For example, if you are opening a [Folder Form Libraries](folder-form-libraries.md), pass an [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md) pointer.</span></span> 
  
<span data-ttu-id="2392b-115">在**OpenFormContainer**返回**IMAPIFormContainer**指针后, 调用[IMAPIFormContainer:: InstallForm](imapiformcontainer-installform.md)或[IMAPIFormContainer:: RemoveForm](imapiformcontainer-removeform.md), 具体取决于要执行的维护。</span><span class="sxs-lookup"><span data-stu-id="2392b-115">After **OpenFormContainer** returns the **IMAPIFormContainer** pointer, call either [IMAPIFormContainer::InstallForm](imapiformcontainer-installform.md) or [IMAPIFormContainer::RemoveForm](imapiformcontainer-removeform.md), depending on the maintenance to be performed.</span></span> <span data-ttu-id="2392b-116">**InstallForm**将窗体服务器添加到库中;**RemoveForm**从库中删除表单服务器。</span><span class="sxs-lookup"><span data-stu-id="2392b-116">**InstallForm** adds a form server to the library; **RemoveForm** deletes a form server from the library.</span></span> 
  

