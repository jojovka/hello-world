# hello-world
Just my first repository

tag
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<window xmlns="http://jmix.io/schema/ui/window"
        xmlns:c="http://jmix.io/schema/ui/jpql-condition"
        caption="msg://plannedWorkBrowse.caption"
        focusComponent="plannedWorksTable">
    <data readOnly="true">
        <collection id="plannedWorksDc"
                    class="kz.eub.moncl.entity.PlannedWork">
            <fetchPlan extends="_base"/>
            <loader id="plannedWorksDl">
                <query>
                    <![CDATA[select e from mcl_PlannedWork e]]>
                </query>
            </loader>
        </collection>

        <collection id="disposableTasksDTODc"
                    class="kz.eub.moncl.entity.DisposableTaskDTO">
            <fetchPlan extends="_base">
                <property name="triggerId"/>
                <property name="hostsName"/>
                <property name="itemsName"/>
                <property name="itemsLastValue"/>
                <property name="priority"/>
                <property name="comments"/>
            </fetchPlan>
            <loader id="disposableTaskDTODl">
                <query>
<!--                    <![CDATA[select e from mcl_DisposableTaskDTO e]]>-->
                </query>
            </loader>
        </collection>
    </data>
    <facets>
        <dataLoadCoordinator auto="true"/>
        <screenSettings id="settingsFacet" auto="true"/>
    </facets>
    <actions>
        <action id="lookupSelectAction"
                caption="msg:///actions.Select"
                icon="LOOKUP_OK"
                primary="true"
                shortcut="${COMMIT_SHORTCUT}"/>
        <action id="lookupCancelAction"
                caption="msg:///actions.Cancel"
                icon="LOOKUP_CANCEL"/>
    </actions>
    <dialogMode height="600"
                width="800"/>
    <layout spacing="true">
        <vbox id="vboxPlannedWork" spacing="false" align="TOP_LEFT">
            <filter id="filter"
                    dataLoader="plannedWorksDl">
                <properties include=".*"/>
            </filter>
            <groupBox caption="Плановые работы"
                      captionAsHtml="true"
                      spacing="true"
                      width="100%"
                      align="TOP_LEFT"
                      collapsable="true"
                      stylename="light">
                <dataGrid id="plannedWorksTable"
                          width="100%"
                          height="260"
                          align="TOP_LEFT"
                          dataContainer="plannedWorksDc"
                          selectionMode="MULTI_CHECK"
                          textSelectionEnabled="true">
                    <actions>
                    </actions>
                    <columns>
                        <column id="btnStart" caption="Старт">
                            <iconRenderer/>
                        </column>
                        <column id="btnFinish" caption="Финиш">
                            <iconRenderer/>
                        </column>
                        <column id="date" property="date"/>
                        <column id="systemName" property="systemName"/>
                        <column id="taskName" property="taskName"/>
                        <column id="plannedWorkDescription" property="plannedWorkDescription">
                            <textRenderer/>
                        </column>
                        <column id="priority" property="priority"/>
                        <column id="scheduledStartTime" property="scheduledStartTime"/>
                        <column id="scheduledEndTime" property="scheduledEndTime"/>
                        <column id="actualStartTime" property="actualStartTime"/>
                        <column id="actualEndTime" property="actualEndTime"/>
                        <column id="comment" property="comment"/>
                        <column id="status" property="status"/>
                        <column id="fullName" property="fullName"/>
                    </columns>
                    <simplePagination/>
                    <buttonsPanel id="buttonsPanel"
                                  alwaysVisible="true">
                        <!--                        <button id="plannedWorksTableRemoveBtn" action="plannedWorksTable.remove" visible="false"/>-->
                    </buttonsPanel>
                </dataGrid>
            </groupBox>
        </vbox>
        <vbox id="vboxDisposableWork" spacing="false" align="BOTTOM_LEFT">
            <groupBox caption="Разовые задачи"
                      captionAsHtml="true"
                      spacing="true"
                      width="100%"
                      align="BOTTOM_LEFT"
                      collapsable="true"
                      stylename="light">
                <dataGrid id="disposableTasksTable"
                          width="100%"
                          height="260"
                          align="BOTTOM_LEFT"
                          dataContainer="disposableTasksDTODc">
                    <actions>
<!--                        <action id="create" type="create"/>-->
<!--                        <action id="edit" type="edit"/>-->
<!--                        <action id="remove" type="remove"/>-->
                    </actions>
                    <buttonsPanel alwaysVisible="true">
<!--                        <button id="disposableTasksTableCreateBtn" action="disposableTasksTable.create"/>-->
<!--                        <button id="disposableTasksTableEditBtn" action="disposableTasksTable.edit"/>-->
<!--                        <button id="disposableTasksTableRemoveBtn" action="disposableTasksTable.remove"/>-->
                    </buttonsPanel>
                    <columns>
<!--                        <column id="btnStartDisposableTask" caption="Старт">-->
<!--                            <iconRenderer/>-->
<!--                        </column>-->
<!--                        <column id="btnFinishDisposableTask" caption="Финиш">-->
<!--                            <iconRenderer/>-->
<!--                        </column>-->
                        <column id="triggerId" property="triggerId"/>
                        <column id="hostsName" property="hostsName"/>
                        <column id="itemsName" property="itemsName"/>
                        <column id="itemsLastValue" property="itemsLastValue"/>
                        <column id="priority" property="priority"/>
                        <column id="comments" property="comments"/>
                    </columns>
                </dataGrid>
            </groupBox>
            <label value="Zabbix" align="BOTTOM_LEFT" stylename="h1"/>
            <browserFrame id="grafanaBrowserFrame" width="AUTO" height="50%" align="BOTTOM_LEFT"
                          referrerpolicy="no-referrer">
                <resource>
                    <url url="https://panel.eub.kz/login"/>
                </resource>
            </browserFrame>
        </vbox>
        <hbox id="lookupActions" spacing="true" visible="false">
            <button action="lookupSelectAction"/>
            <button action="lookupCancelAction"/>
        </hbox>
    </layout>
</window>
