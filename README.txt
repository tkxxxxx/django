# django

http://127.0.0.1:8000/taskCalendar/

python manage.py startapp sample => アプリケーションの作成
python manage.py migrate         => DBマイグレーションの実行
python manage.py shell           => インタラクティブShellの起動
python manage.py runserver       => 開発サーバーの起動


    if mode == 1:
        # 変更の場合

        # 機種グループマスタを取得する。
        groupInfo = Craftgroup.objects.filter(craftgroup = craftGroup)

        # ソートキー
        sortKey = groupInfo[0].sortkey

        # 検索されたデータを削除する。
        groupInfo.delete()

        # 機種グループマスタを登録する。
        Craftgroup.objects.create(craftgroup = groupName, classdiff = classDiff, sortkey = sortKey)

        # 機種マスタを検索する。
        craftModel = Craftmodel.objects.filter(craftgroup = craftGroup)

        # 機種マスタを更新する。
        craftModel.update(craftgroup = groupName)

        # 機種マスタを検索する。
        newModel = Craftmodel.objects.filter(craftgroup = craftGroup)

        # 機種マスタの件数
        content['modelRowCount'] = len(newModel)
