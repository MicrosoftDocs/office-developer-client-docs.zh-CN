---
title: Append 方法 (ADOX Procedures)
TOCTitle: Append Method (ADOX Procedures)
ms:assetid: a93b31bb-e41a-5152-abe7-dd7c2b2fcd0a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249783(v=office.15)
ms:contentKeyID: 48546919
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5c1afc7aeea90fc152df7d8f7b1601bf3753b3a3
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465880"
---
# <a name="append-method-adox-procedures"></a><span data-ttu-id="013e0-102">Append 方法 (ADOX Procedures)</span><span class="sxs-lookup"><span data-stu-id="013e0-102">Append Method (ADOX Procedures)</span></span>


<span data-ttu-id="013e0-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="013e0-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="013e0-104">将新的 [Procedure](procedure-object-adox.md) 对象添加到 [Procedures](procedures-collection-adox.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="013e0-104">Adds a new [Procedure](procedure-object-adox.md) object to the [Procedures](procedures-collection-adox.md) collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="013e0-105">语法</span><span class="sxs-lookup"><span data-stu-id="013e0-105">Syntax</span></span>

<span data-ttu-id="013e0-106">*过程*。追加*名称*，*命令*</span><span class="sxs-lookup"><span data-stu-id="013e0-106">*Procedures*.Append*Name*, *Command*</span></span>

## <a name="parameters"></a><span data-ttu-id="013e0-107">参数</span><span class="sxs-lookup"><span data-stu-id="013e0-107">Parameters</span></span>

  - <span data-ttu-id="013e0-108">*Name*</span><span class="sxs-lookup"><span data-stu-id="013e0-108">*Name*</span></span>

  - <span data-ttu-id="013e0-109">**String** 值，指定要创建并追加的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="013e0-109">A **String** value that specifies the name of the procedure to create and append.</span></span>

  - <span data-ttu-id="013e0-110">*Command*</span><span class="sxs-lookup"><span data-stu-id="013e0-110">*Command*</span></span>

  - <span data-ttu-id="013e0-111">一个 ADO [Command](command-object-ado.md) 对象，表示要创建并追加的过程。</span><span class="sxs-lookup"><span data-stu-id="013e0-111">An ADO [Command](command-object-ado.md) object that represents the procedure to create and append.</span></span>

## <a name="remarks"></a><span data-ttu-id="013e0-112">备注</span><span class="sxs-lookup"><span data-stu-id="013e0-112">Remarks</span></span>

<span data-ttu-id="013e0-113">使用在 **Command** 对象中指定的名称和属性在数据源中创建一个新过程。</span><span class="sxs-lookup"><span data-stu-id="013e0-113">Creates a new procedure in the data source with the name and attributes specified in the **Command** object.</span></span>

<span data-ttu-id="013e0-p101">如果用户指定的命令文本表示视图而非过程，则其行为取决于所使用的提供程序。如果该提供程序不支持保留命令，则 **Append** 将失败。</span><span class="sxs-lookup"><span data-stu-id="013e0-p101">If the command text that the user specifies represents a view rather than a procedure, the behavior is dependent upon the provider being used. **Append** will fail if the provider does not support persisting commands.</span></span>


> [!NOTE]
> <P><span data-ttu-id="013e0-116">使用 Microsoft Jet OLE DB 提供程序，将允许<STRONG>Procedures</STRONG>集合的<STRONG>Append</STRONG>方法，您可以在<EM>命令</EM>参数中指定<STRONG>视图</STRONG>，而不是<STRONG>过程</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="013e0-116">When using the OLE DB Provider for Microsoft Jet, the <STRONG>Procedures</STRONG> collection <STRONG>Append</STRONG> method will allow you to specify a <STRONG>View</STRONG> rather than a <STRONG>Procedure</STRONG> in the <EM>Command</EM> parameter.</span></span> <span data-ttu-id="013e0-117">该 <STRONG>View</STRONG> 将添加到数据源，并将添加到 <STRONG>Procedures</STRONG> 集合。</span><span class="sxs-lookup"><span data-stu-id="013e0-117">The <STRONG>View</STRONG> will be added to the data source and will be added to the <STRONG>Procedures</STRONG> collection.</span></span> <span data-ttu-id="013e0-118">执行 <STRONG>Append</STRONG> 之后，如果刷新 <STRONG>Procedures</STRONG> 和 <STRONG>Views</STRONG> 集合，可以看见该 <STRONG>View</STRONG> 不再位于 <STRONG>Procedures</STRONG> 集合中，而是出现在 <STRONG>Views</STRONG> 集合中。</span><span class="sxs-lookup"><span data-stu-id="013e0-118">After the <STRONG>Append</STRONG>, if the <STRONG>Procedures</STRONG> and <STRONG>Views</STRONG> collections are refreshed, the <STRONG>View</STRONG> will no longer be in the <STRONG>Procedures</STRONG> collection and will appear in the <STRONG>Views</STRONG> collection.</span></span></P>


