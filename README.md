# Android_Review_2
Fragment

1. code in MainActivity.kt
 
        package com.example.android.katesapp
        
        [default modules]
        import androidx.appcompat.app.AppCompatActivity
        import android.os.Bundle
        
        [add databinding module]
        import androidx.databinding.DtatBindingUtil
        
        [add navigation module]
        import com.example.android.navigation.databinding.ActivityDataBinding
        
        class MainActivity: AppCompatActivity(){
          
          override fun onCreate(saveInstanceState: Bundle?){
          
            super.onCreate(saveInstanceState)
            val binding = DataBindingUtil.setContentView<ActivityMainBinding>(this, R.layout.activity_main)
            
            // TODO:
            // create TitleFragment.kt and its related UI layout called fragemt_title
          
          }
        
        }
        
2. Select File->New->Fragment->Fragment (Blank) to create a new Fragment UI layout called fragment_title.xml instead of Activity layout. And add ConstraintLayout uder layer of layout inside it. Beside it, the layout will use navigation modules by default.
 
        <?xml encoding="utf-8"?>
        
        <layout
          xmlns:android=""
          xmlns:app=""
          xmlns:tools=""
          tools:context="com.example.android.katesapp.TitleFragment"
        >
          
          <android.constraintlayout.widget.ConstraintLayout
            android:id="@+id/titleConstraint"
          />
          
        </layout>

3. add <fragment> UI tag in layout called activity_main.xml.
  
       <?xml encoding="utf-8" xmlns:android="" xmlns:app=""?>
       
       <layout>
        <LinearLayout
          android:orientation="vertical"
        >
          <fragment
            android:id="@id/titleFragment"
            android:name="com.example.android.katesapp.TitleFragment"
          />
        </LnearLayout>
       </layout>

4. add Button and ImageView in fragment_title.xml.
  
          <?xml encoding="utf-8"?>
        
          <layout
            xmlns:android=""
            xmlns:app=""
            xmlns:tools=""
            tools:context="com.example.android.katesapp.TitleFragment"
          >
          
            <android.constraintlayout.widget.ConstraintLayout
              android:id="@+id/titleConstraint"
              
              <Button/>
              <ImageView/>>
              
            />
          
         </layout>
  

        }
        
5. use DataBindingUtil.inflate to inflate (or return) the titleFragment in onCreateView phase in TitleFragment.kt, code the TitleFragment which is a subclass of the Fragment class.

       package com.example.android.katesapp
       
       [default modules]
       import androidx.fragment.app.Fragment
       import android.os.Bundle
       
       // Mian feature hereby for Fragment
       [databinding modules]
       import androidx.databinding.DataBindingUtil
       import com.example.android.katesapp.databinding.FragmentTitleBinding
       
       [view modules]
       import andorid.view.View
       import android.view.ViewGroup
       
       // Inflator feature
       import android.view.LayoutInflater
       
       class TitleFragment: Fragment(){
       
         override fun onCreateView(inflator: LayoutInfator, container: ViewGroup?, savediInstanceState: Bundle?): View?{
         
           val binding = DataBindingUtil.inflate<FragmentTitleBinding>(inflater, R.layout.fragment_title, container, false)
           
           // means fragment_title.xml layout
           return binding.root
         
         }
      
       }
       
       
       




