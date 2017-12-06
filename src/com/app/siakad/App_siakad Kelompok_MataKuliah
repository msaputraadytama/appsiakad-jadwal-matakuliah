package com.app.siakad.entities;

import java.sql.SQLException;
import java.util.ArrayList;
import javax.swing.JOptionPane;
import com.app.siakad.database.KoneksiDB;

/**
 *
 * 
 */
public class tbmstkelompokmk extends KoneksiDB{
    
    public String kd_tbmstkelompokmk;
    public String tbmstkelompokmk;
    
    public void select(){
        tbljurusan.setColumnIdentifiers(new Object[]{"Kode", "Nama mstkelompokmk"});
        try{
            conn = getConnection();
            query = "select * from tbmstkelompokmk";
            stat = conn.prepareStatement(query);
            res = stat.executeQuery(query);
            list = new ArrayList<>();
            while(res.next()){
                tbmstkelompokmk= res.getString(1);
                tbmstkelompokmk = res.getString(2);
                
                list.add(new Object[]{kd_tbmstkelompokmk, tbmstkelompokmk});
            }
            stat.close();
        }catch(SQLException ex){
            JOptionPane.showMessageDialog(null, "Error method select() : " + ex);
        }
    }
    
    public void insert_update(){
        try{
            conn = getConnection();
            if(isUpdate == false){
                query = " insert into tbmstkelompokmk values(?,?) ";
            }else{
                query = " update tbmstkelompokmk set kd_mstkelompokmk=?, mstkelompokmk=? "
                        + " where kd_tbmstkelompokmk='"+kd_tbmstkelompokmk+"' ";
            }
            stat = conn.prepareStatement(query);
            stat.setString(1, kd_tbmstkelompokmk);
            stat.setString(2, tbmstkelompokmk);
            stat.executeUpdate();
            stat.close();
        }catch(SQLException ex){
            JOptionPane.showMessageDialog(null, "Error method insert_update() : " + ex);
        }
    }
    
    public void delete(String kd_jur){
        try{
            conn = getConnection();
            query = "delete from tbmstkelompokmk where kd_mstkelompokmk='"+kd_tbmstkelompokmk+"' ";
            stat = conn.prepareStatement(query);
            stat.executeUpdate();
            stat.close();
        }catch(SQLException ex){
            JOptionPane.showMessageDialog(null, "Error method delete() : " + ex);
        }
    }
    
    public String[] Keymstkelompokmk, mstkelompokmk;
    public void listJurusan(){
        try{
            conn = getConnection();
            query = "select * from tbmstkelompokmk";
            stat = conn.prepareStatement(query);
            res = stat.executeQuery(query);
            int i = 1;
            while(res.next()){
                mstkelompokmk[i] = res.getString(2);
                i++;
            }
            res.first();
            Keymstkelompokmk = new String[i+1];
            for(int x=1 ; x<i ; x++){
                Keymstkelompokmk[x] = res.getString(1);
                res.next();
            }
            stat.close();
        } catch (SQLException ex) {
            System.out.println("Error Method listmstkelompokmk : "+ex);
        }
    }
    
}
