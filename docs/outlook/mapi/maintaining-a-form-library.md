---
title: 维护表单库
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8488f7ec-e44b-4d1a-ba42-baea8c71d350
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5ccb5a2881d3cef3ff21a106e7e9ea33e0aedd9e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776161"
---
# <a name="maintaining-a-form-library"></a><span data-ttu-id="f9305-103">维护表单库</span><span class="sxs-lookup"><span data-stu-id="f9305-103">Maintaining a Form Library</span></span>

  
  
<span data-ttu-id="f9305-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f9305-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f9305-105">表单库保留所有窗体的重要信息： 其属性、 其谓词和所在服务器的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="f9305-105">A form library holds all of the important information about a form: its properties, its verbs, and its server's executable files.</span></span> <span data-ttu-id="f9305-106">某些客户端允许其用户进行维护、 安装或删除表单服务器。</span><span class="sxs-lookup"><span data-stu-id="f9305-106">Some clients allow their users to maintain, install, or remove form servers.</span></span> <span data-ttu-id="f9305-107">如果您想要向用户提供此功能，您必须有权：</span><span class="sxs-lookup"><span data-stu-id="f9305-107">If you want to offer this feature to your users, you must have access to:</span></span>
  
- <span data-ttu-id="f9305-108">窗体服务器的配置文件、 的文件。配置扩展。</span><span class="sxs-lookup"><span data-stu-id="f9305-108">The form server's configuration file, a file with the .CFG extension.</span></span>
    
- <span data-ttu-id="f9305-109">表单库的容器对象，实现的对象[IMAPIFormContainer: IUnknown](imapiformcontaineriunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="f9305-109">The form library's container object, an object that implements the [IMAPIFormContainer : IUnknown](imapiformcontaineriunknown.md) interface.</span></span> 
    
<span data-ttu-id="f9305-110">若要访问的配置文件或向其使用路径名任何方法是方便。</span><span class="sxs-lookup"><span data-stu-id="f9305-110">To access the configuration file or a pathname to it, use whatever means are convenient.</span></span> <span data-ttu-id="f9305-111">通常情况下，客户端向用户显示一个对话框，安装和删除还可用于提示用户输入配置文件的位置的窗体服务器。</span><span class="sxs-lookup"><span data-stu-id="f9305-111">Usually, clients present the user with a dialog box for installing and removing form servers that can also be used to prompt the user for the location of the configuration file.</span></span>
  
<span data-ttu-id="f9305-112">若要访问表单库的容器，调用窗体经理[IMAPIFormMgr::OpenFormContainer](imapiformmgr-openformcontainer.md)方法。</span><span class="sxs-lookup"><span data-stu-id="f9305-112">To access the form library's container, call the form manager's [IMAPIFormMgr::OpenFormContainer](imapiformmgr-openformcontainer.md) method.</span></span> <span data-ttu-id="f9305-113">传入的枚举值，以指定的表单库，若要打开，如有必要，指向窗体管理器应使用打开的表单库的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="f9305-113">Pass in an enumeration value to specify which form library to open, and if necessary, a pointer to the object that the form manager should use to open the form library.</span></span> <span data-ttu-id="f9305-114">例如，如果您打开[文件夹表单库](folder-form-libraries.md)，传递[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)指针。</span><span class="sxs-lookup"><span data-stu-id="f9305-114">For example, if you are opening a [Folder Form Libraries](folder-form-libraries.md), pass an [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md) pointer.</span></span> 
  
<span data-ttu-id="f9305-115">**OpenFormContainer**返回**IMAPIFormContainer**指针后，调用[IMAPIFormContainer::InstallForm](imapiformcontainer-installform.md)或[IMAPIFormContainer::RemoveForm](imapiformcontainer-removeform.md)，具体取决于要执行的维护。</span><span class="sxs-lookup"><span data-stu-id="f9305-115">After **OpenFormContainer** returns the **IMAPIFormContainer** pointer, call either [IMAPIFormContainer::InstallForm](imapiformcontainer-installform.md) or [IMAPIFormContainer::RemoveForm](imapiformcontainer-removeform.md), depending on the maintenance to be performed.</span></span> <span data-ttu-id="f9305-116">**InstallForm**将窗体服务器添加到库中;**RemoveForm**从库中删除的窗体服务器。</span><span class="sxs-lookup"><span data-stu-id="f9305-116">**InstallForm** adds a form server to the library; **RemoveForm** deletes a form server from the library.</span></span> 
  

