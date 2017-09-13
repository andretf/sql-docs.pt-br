---
title: Selecionar dispositivo de backup | Microsoft Docs
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-backup-restore
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.swb.selectbackupdevice.f1
ms.assetid: 7887c9fd-15ce-4cc8-b069-845c1d09088c
caps.latest.revision: 27
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 804733fbf0d86e743ad029e40f50f93b040fd124
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2017

---
# <a name="select-backup-device"></a>Selecionar Dispositivo de Backup
  Use a caixa de diálogo **Selecionar Dispositivo de Backup** para selecionar um dispositivo lógico de backup para a operação de restauração.  
  
 O dispositivo lógico de backup é definido pelo usuário e correspondente a um dispositivo físico, que pode ser uma unidade de fita ou de disco fornecidas pelo sistema operacional.  
  
> [!NOTE]  
>  Para que um backup possa utilizar vários dispositivos de backup, todos precisam corresponder a um único tipo de dispositivo.  
  
 **Para usar o SQL Server Management Studio para exibir o conteúdo de um dispositivo de backup**  
  
-   [Exibir o conteúdo de um arquivo ou fita de backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [Exibir as propriedades e o conteúdo de um dispositivo de backup lógico &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a>Opções  
 **Dispositivo de backup**  
 Na caixa de listagem, selecione o nome de um dispositivo lógico de backup do qual você deseja restaurar.  
  
 Para obter informações sobre como exibir o conteúdo de um dispositivo de backup, veja [Exibir as propriedades e o conteúdo de um dispositivo de backup lógico &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md).  
  
## <a name="remarks"></a>Comentários  
 Caso não se observe um dispositivo lógico de backup que contenha um backup procurado na lista, isso indica que o backup pode ter sido gravado diretamente em um ou mais arquivos ou unidades de fita. Nesse caso, cancele a caixa de diálogo **Selecionar Dispositivo de Backup** . Na caixa de diálogo **Especificar Backup** , selecione **Arquivo** ou **Fita** na caixa de listagem **Mídia do backup** .  
  
## <a name="see-also"></a>Consulte também  
 [Dispositivos de backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/backup-devices-sql-server.md)  
  
  